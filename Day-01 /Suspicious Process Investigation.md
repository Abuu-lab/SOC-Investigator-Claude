# DAY 1

## CTF 001 — SUSPICIOUS PROCESS INVESTIGATION

### Posisi dalam Program

**Track:** CTF + SOC Investigator
**Month:** 1
**Week:** 1
**Day:** 1
**Level:** Beginner → Developing

Fondasi Windows, Process Investigation, Event Log, Authentication, dan Sysmon yang sudah dipelajari sebelumnya dianggap sebagai **prerequisite**.

Hari ini tidak mengulang Computer Fundamentals.

Hari ini mulai masuk ke **investigasi CTF yang sesungguhnya**.

---

# 1. TARGET PEMBELAJARAN

Pada akhir challenge ini saya harus mampu:

* membaca Sysmon Event ID 1
* memahami ProcessId
* memahami ParentProcessId
* membangun process tree
* memahami ParentImage
* membaca ParentCommandLine
* membaca CommandLine
* menghubungkan process dengan User
* memperhatikan IntegrityLevel
* menemukan process anomaly
* melakukan pivot dari satu process ke process lain
* membuat hypothesis
* menguji hypothesis berdasarkan evidence
* menentukan confidence
* menentukan investigative next step
* mendokumentasikan temuan

Prinsip utama:

```text
Evidence First
       ↓
Observation
       ↓
Hypothesis
       ↓
Testing
       ↓
Correlation
       ↓
Conclusion
```

Bukan:

```text
Guess
 ↓
Flag
 ↓
Cari pembenaran
```

Pola tersebut mengikuti fondasi investigator yang sudah ditetapkan dalam roadmap, terutama observe, collect, hypothesize, test, correlate, conclude, dan document.

---

# 2. MATERI UTAMA

## A. Sysmon Event ID 1

Sysmon Event ID 1 berkaitan dengan **Process Creation**.

Di challenge ini kita akan memanfaatkan field:

```text
TimeCreated
ProcessId
ParentProcessId
Image
CommandLine
User
IntegrityLevel
ParentImage
ParentCommandLine
SHA256
```

Jangan membaca setiap field sebagai informasi terpisah.

Yang kita cari adalah **hubungan antar-field**.

---

# 3. PROCESS ID

Contoh:

```text
ProcessId = 11204
```

PID merupakan identifier process pada saat process tersebut berjalan.

Misalnya:

```text
powershell.exe
PID 11204
```

Jangan berhenti di sini.

Kita perlu mencari:

```text
PPID = ?
```

karena context process sering jauh lebih berguna daripada nama process itu sendiri.

---

# 4. PARENT PROCESS ID

Misalnya:

```text
ProcessId        = 11204
ParentProcessId  = 11168
```

Artinya process `11204` mempunyai parent process `11168`.

Kemudian kita cari event:

```text
ProcessId = 11168
```

Dari sana kita dapat parent berikutnya.

Inilah dasar process-tree investigation.

---

# 5. PROCESS TREE

Misalnya hasil korelasi menunjukkan:

```text
explorer.exe
     ↓
WINWORD.EXE
     ↓
cmd.exe
     ↓
powershell.exe
     ↓
rundll32.exe
```

Kita tidak langsung mengatakan:

> malware

Yang pertama dicatat adalah:

> **Observed process chain.**

Kemudian baru dianalisis apakah chain tersebut normal atau suspicious.

---

# 6. COMMAND LINE

Nama executable kadang terlihat biasa.

Contoh:

```text
powershell.exe
```

Tetapi CommandLine dapat memberi context lebih besar.

Misalnya:

```text
powershell.exe -NoProfile -Command Get-Process
```

dan:

```text
powershell.exe -NoProfile -ExecutionPolicy Bypass -File "C:\Users\riza\AppData\Local\Temp\update.ps1"
```

Keduanya sama-sama PowerShell.

Namun context-nya berbeda.

Karena itu:

```text
Image ≠ Investigation
```

Lebih tepat:

```text
Image
+
CommandLine
+
Parent
+
User
+
Path
+
Time
```

---

# 7. USER CONTEXT

Kita juga perlu melihat:

```text
User = ?
```

Sebuah process dijalankan oleh siapa.

Contohnya:

```text
LAB\riza
```

atau:

```text
NT AUTHORITY\SYSTEM
```

User context membantu menjawab:

> aktivitas tersebut dilakukan dalam security context siapa.

Tetapi:

```text
High privilege ≠ automatically malicious
```

Dan:

```text
Normal user ≠ automatically safe
```

Context tetap menjadi pusat analisis.

---

# 8. INTEGRITY LEVEL

Contoh:

```text
Medium
High
System
```

Integrity Level membantu memahami tingkat security context process.

Tetapi kembali lagi:

```text
High/System ≠ automatically malicious
```

Integrity hanya satu bagian dari evidence.

---

# 9. PARENT-CHILD CORRELATION

Ini merupakan skill utama Day 1.

Contoh:

```text
Parent:
WINWORD.EXE

Child:
cmd.exe
```

Kemudian:

```text
Parent:
cmd.exe

Child:
powershell.exe
```

Kemudian:

```text
Parent:
powershell.exe

Child:
rundll32.exe
```

Kita memperoleh:

```text
WINWORD.EXE
    ↓
cmd.exe
    ↓
powershell.exe
    ↓
rundll32.exe
```

Sekarang pertanyaan investigasi yang relevan bukan:

> "Apakah powershell berbahaya"

melainkan:

```text
Mengapa process tersebut muncul
Apa parent-nya
Apa command-line-nya
Apa file/path yang terlibat
Siapa user-nya
Kapan sequence terjadi
Apa hubungan antar-event
```

---

# 10. OBSERVATION VS CONCLUSION

Ini salah satu konsep terpenting dalam program kita.

### Observation

Hal yang benar-benar terlihat dari evidence.

Contoh:

```text
WINWORD.EXE membuat cmd.exe.
cmd.exe membuat PowerShell.
PowerShell dijalankan dengan ExecutionPolicy Bypass.
```

### Conclusion

Interpretasi terhadap observation.

Contoh:

```text
Sequence tersebut suspicious dan berpotensi menunjukkan
execution chain yang perlu diperiksa lebih lanjut.
```

Jangan mencampur keduanya.

Format kerja yang bagus:

```text
OBSERVATION
↓
INTERPRETATION
↓
HYPOTHESIS
↓
VALIDATION
↓
CONCLUSION
```

---

# 11. SUSPICIOUS ≠ MALICIOUS

Day 1 ini sengaja melatih kamu menghindari kesimpulan prematur.

Misalnya:

```text
powershell.exe
```

terlihat suspicious.

Belum berarti malicious.

Atau:

```text
ExecutionPolicy Bypass
```

terlihat mencolok.

Tetap perlu context.

Kita mencari **kombinasi evidence**.

Contoh pola:

```text
Office application
       ↓
cmd
       ↓
PowerShell
       ↓
script dari Temp
       ↓
rundll32
       ↓
DLL
```

Semakin banyak evidence yang saling mendukung, semakin kuat hypothesis.

---

# 12. HYPOTHESIS

Gunakan format:

```text
HYPOTHESIS:
...

SUPPORTING EVIDENCE:
1. ...
2. ...
3. ...

COUNTER-EVIDENCE:
1. ...

CONFIDENCE:
Low / Medium / High
```

Tujuannya supaya kamu terbiasa menyadari bahwa evidence dapat:

* mendukung hypothesis
* melemahkan hypothesis
* belum cukup untuk mengambil verdict

---

# 13. CHALLENGE SCENARIO

Sebuah workstation Windows menghasilkan alert:

```text
ALERT

Host:
WIN-LAB-01

Alert Type:
Suspicious Process Activity

Approximate Time:
09:42

User:
LAB\riza
```

Informasi tersebut sengaja minim.

Tidak ada nama malware.

Tidak ada IOC.

Tidak ada verdict.

Kamu berperan sebagai analyst yang menerima alert awal.

---

# 14. ARTIFACT

Gunakan dataset:

[Download CTF Day 1 — Suspicious Process Investigation](sandbox:/mnt/data/CTF_Day13/CTF_Day13_Suspicious_Process.zip)

Artifact:

```text
sysmon_event1.csv
README.txt
```

SHA-256 artifact:

```text
5c6ebaa8b1973d2ebfcfdccb9d6ad53c44ca2cb02c1baa450cc01b9e0a11fa68
```

Dataset merupakan simulasi historical Sysmon telemetry.

---

# 15. ATURAN KEAMANAN

Dataset hanya digunakan sebagai evidence.

Jangan mengeksekusi command line yang muncul di dalam log.

Terutama jangan menjalankan:

```text
.exe
.ps1
.cmd
.dll
```

yang hanya tertulis sebagai evidence.

Kita sedang melakukan **analysis**, bukan execution.

---

# 16. LANGKAH AWAL

Ekstrak:

```bash
unzip CTF_Day13_Suspicious_Process.zip
```

Masuk ke folder hasil ekstraksi lalu:

```bash
ls -lah
```

Periksa CSV:

```bash
head sysmon_event1.csv
```

Untuk tampilan lebih nyaman:

```bash
column -s, -t < sysmon_event1.csv | less -S
```

Kamu bebas memakai:

```text
grep
awk
cut
sort
uniq
less
cat
Python
PowerShell
```

Pemilihan tool adalah bagian dari skill.

---

# 17. INVESTIGATION FLOW

Gunakan alur:

```text
STEP 1
Inspect Dataset
        ↓
STEP 2
Identify Processes
        ↓
STEP 3
Build Process Tree
        ↓
STEP 4
Locate Anomaly
        ↓
STEP 5
Pivot to Parent
        ↓
STEP 6
Pivot to Child
        ↓
STEP 7
Analyze CommandLine
        ↓
STEP 8
Check User Context
        ↓
STEP 9
Build Hypothesis
        ↓
STEP 10
Determine Confidence
```

Jangan lompat langsung ke Step 9.

---

# 18. OBJECTIVE CHALLENGE

Kamu harus menemukan:

## A. Suspicious Process

```text
ProcessId:
Image:
```

## B. Process Chain

Tulis:

```text
Parent
  ↓
Child
  ↓
Child
  ↓
Child
```

## C. User Context

```text
User:
IntegrityLevel:
```

## D. CommandLine

Tulis command line yang paling relevan.

## E. Anomaly

Jelaskan:

```text
Apa yang terlihat tidak biasa
```

## F. Evidence

Minimal tiga evidence.

## G. Hypothesis

Jelaskan kemungkinan yang terjadi.

## H. Confidence

```text
Low
Medium
High
```

## I. Next Step

Pilih satu evidence tambahan yang paling bernilai untuk investigasi berikutnya.

Ini mulai melatih prinsip **Need to Know** dan **Pivot**, yang nanti akan menjadi dasar investigasi SOC yang jauh lebih besar.

---

# 19. SUBMISSION FORMAT

Kirim hasil investigasimu dengan format:

```text
=== DAY 1 CTF 001 ===

1. INITIAL OBSERVATION

...

2. SUSPICIOUS PROCESS

ProcessId:
Image:

3. PROCESS TREE

...

4. USER CONTEXT

User:
IntegrityLevel:

5. COMMAND LINE

...

6. ANOMALY

...

7. EVIDENCE

Evidence 1:
Evidence 2:
Evidence 3:

8. HYPOTHESIS

...

9. CONFIDENCE

Low / Medium / High

10. NEXT INVESTIGATIVE STEP

...

11. TOOLS / COMMANDS USED

...
```

Tambahkan output command yang menurutmu paling penting.

**Jangan hanya mengirim jawaban akhir.**

Saya ingin melihat jejak reasoning-mu.

---

# 20. SISTEM HINT

Saya tidak memberi hint sebelum kamu meminta.

Urutannya:

```text
Challenge
↓
Investigation
↓
Jawabanmu
↓
Evaluasi
↓
Hint 1
↓
Hint 2
↓
Hint 3
↓
Solution
↓
Post-mortem
```

Kalau jawabanmu salah, saya akan menunjukkan bagian reasoning yang bermasalah tanpa langsung membocorkan solusi.

Kalau jawabanmu benar tetapi cara berpikirmu terlalu loncat, saya tetap akan mengoreksinya.

---

# 21. PENILAIAN

Day 1 dinilai berdasarkan:

```text
Technical Skill
Investigation Skill
Reasoning
Evidence Usage
Accuracy
Efficiency
Documentation
```

Skala:

```text
Beginner
Developing
Competent
Strong
Junior-SOC-Level
```

Flag bukan satu-satunya ukuran.

Roadmap-mu secara eksplisit menetapkan bahwa kualitas reasoning, penggunaan evidence, hypothesis testing, correlation, dan documentation harus menjadi indikator utama.

---

# 22. MILESTONE 18 BULAN

## MONTH 1

### WEEK 1

### DAY 1

**Challenge:** CTF 001
**Topic:** Suspicious Process Investigation

### Materi Dipelajari

* Sysmon Event ID 1
* Process Creation telemetry
* ProcessId
* ParentProcessId
* ParentImage
* ParentCommandLine
* Image
* CommandLine
* User
* IntegrityLevel
* SHA-256 telemetry
* Process Tree
* Parent-child relationship
* Historical endpoint telemetry
* Process context
* Observation vs conclusion
* Suspicious ≠ malicious
* Evidence-first investigation
* Hypothesis-driven investigation
* Confidence assessment
* Investigative next step

### Skill SOC

* Initial alert triage
* Endpoint process investigation
* Historical telemetry analysis
* Process correlation
* User correlation
* CommandLine analysis
* Anomaly identification
* Evidence-based reasoning

### Skill CTF

* Challenge triage
* Dataset inspection
* Evidence extraction
* Process-tree reasoning
* Pivoting
* Pattern recognition
* Technical documentation

### Tools

* Linux command line
* `unzip`
* `ls`
* `head`
* `column`
* `less`
* `grep`
* `awk`
* `cut`
* `sort`
* `uniq`
* Python / PowerShell sebagai opsi

### Status

```text
[ ] Belum dikerjakan
[ ] Selesai dengan Hint
[ ] Selesai mandiri
[ ] Competent
[ ] Mastered
[ ] Needs Review
```

### Evaluasi

```text
Technical Skill:
...

Investigation Skill:
...

Reasoning:
...

Evidence Usage:
...

Accuracy:
...

Efficiency:
...

Documentation:
...

Kesalahan utama:
...

Kebiasaan investigasi yang sudah baik:
...

Skill yang perlu diperkuat:
...
```

---

# PRINSIP PROGRAM MULAI DAY 1

```text
FLAG = OUTPUT

REASONING = SKILL

EVIDENCE = DASAR

CORRELATION = SENJATA

HYPOTHESIS = ARAH

VALIDATION = PENGUJI

DOCUMENTATION = BUKTI KERJA
```

Target akhirnya tetap seperti roadmap besar: bukan sekadar mampu memperoleh flag, melainkan mampu menghadapi unfamiliar challenge, melakukan triage, memilih pivot, menghubungkan evidence, dan bekerja di bawah tekanan waktu sampai level tournament.

**DAY 1 dimulai sekarang.**
