



# DAY 2
## FACT vs INFERENCE • PRECISION • MEMORY • ADVERSARY THINKING

Mulai hari ini saya ubah sedikit pola evaluasinya.

Nanti setelah kamu mengirim jawaban, saya tidak hanya akan memberi nilai. Untuk setiap bagian yang keliru atau kurang tajam, saya akan berikan:

**Jawabanmu → Penilaian → Letak kesalahan → “Seharusnya kamu menjawab begini...” → Alasan → Versi investigator yang lebih kuat.**

Jadi kamu tidak cuma tahu **salahnya di mana**, tetapi juga melihat **bentuk jawaban yang menurut saya ideal**.

Untuk durasi, catat waktu mulai dan waktu selesai seperti kemarin. Setelah selesai cukup tulis misalnya:

**Durasi: 54 menit**

Target Day 2 sekitar **45 sampai 65 menit**. Tidak perlu mengejar waktu mati-matian.

---

# BAGIAN 1
## MICRO THEORY: FACT, OBSERVATION, INFERENCE, HYPOTHESIS

Hari ini kita memperketat satu garis pemisah:

> **Apa yang diketahui**
>
> **Apa yang dilihat**
>
> **Apa yang disimpulkan**
>
> **Apa yang baru diduga**

Gunakan empat lapisan:

### FACT
Informasi yang diberikan sumber.

### OBSERVATION
Hal yang dapat kita deskripsikan dari evidence tanpa memasukkan motif atau makna.

### INFERENCE
Interpretasi yang kita tarik dari fakta atau observation.

### HYPOTHESIS
Kemungkinan penjelasan yang masih harus diuji.

Kesalahan investigator yang sering terjadi justru begini:

```text
FACT
↓
INFERENCE
↓
dianggap FACT
```

Contoh:

> “File baru muncul pada pukul 22:14.”

Itu fact.

> “File tersebut mencurigakan.”

Itu inference.

> “Employee memasukkan malware.”

Itu hypothesis.

Tiga hal tersebut **bukan benda yang sama**.

---

# BAGIAN 2
## FACT OR INFERENCE

Baca masing-masing pernyataan.

Tentukan:

**F = Fact**  
**I = Inference**  
**H = Hypothesis**

### A

1. `User_A` login pada pukul 23:41.
2. Login dilakukan di luar jam kerja normal.
3. User_A kemungkinan sedang bekerja lembur.
4. User_A sengaja menyembunyikan aktivitas.
5. Event log mencatat akses ke folder `Finance`.
6. Aktivitas tersebut berpotensi berkaitan dengan pekerjaan.
7. Tidak ada approval lembur pada sistem HR.
8. User_A melakukan aktivitas tidak sah.

### Tugas

Tulis:

```text
A1:
A2:
A3:
...
A8:
```

Lalu pilih **dua pernyataan yang menurutmu paling berbahaya bila investigator salah menganggapnya sebagai fact**, dan berikan alasannya.

---

# BAGIAN 3
## PRECISION DRILL 2

Di Day 1 kamu cukup baik membandingkan string, tetapi mulai kehilangan detail ketika string tersebut masuk ke reasoning.

Sekarang levelnya dinaikkan.

Perhatikan:

```text
Host A: FIN-SRV-014
Host B: FIN-SRV-041

IP A: 10.20.14.41
IP B: 10.20.14.14

User A: riza.hermawan
User B: riza_hermawan

File A: payroll_2026.xlsx
File B: payroll_2025.xlsx

Time A: 21:17:42
Time B: 21:17:24
```

### Tugas

Untuk setiap pasangan tuliskan:

**B1.** karakter atau bagian yang berbeda  
**B2.** mana yang lebih mudah salah dibaca  
**B3.** dampak analytical apabila investigator salah mencatatnya

Jangan menggunakan jawaban umum seperti “bisa membingungkan”.

Sebutkan konsekuensi konkretnya.

---

# BAGIAN 4
## TRACE THE EVIDENCE

Sekarang sebuah kasus.

```text
09:03
employee_budi login ke FIN-WS-021

09:05
employee_budi membuka
\\finance\budget_2026

09:07
employee_budi membuka file
budget_internal.xlsx

09:11
akun employee_budi melakukan login
di FIN-WS-067

09:13
budget_internal.xlsx tercatat diakses

09:18
employee_budi logout dari FIN-WS-021
```

Employee kemudian menyatakan:

> “Pagi itu saya hanya menggunakan workstation saya sendiri.”

### Tugas

Pisahkan menjadi:

**C1. Facts**

Minimal 5.

**C2. Observations**

Minimal 3.

**C3. Anomalies**

Minimal 2.

**C4. Inferences**

Minimal 2.

**C5. Hypotheses**

Minimal 3.

Salah satu hypothesis harus innocent explanation.

**C6. Evidence gaps**

Minimal 5 informasi yang belum kita miliki.

**C7. Verification priority**

Pilih **3 evidence** yang paling layak diperiksa lebih dahulu.

Berikan urutan:

```text
Priority 1:
Priority 2:
Priority 3:
```

---

# BAGIAN 5
## THE DANGEROUS CONCLUSION

Baca kalimat investigator berikut:

> “Budi login di dua workstation dalam waktu yang hampir berdekatan. Berarti credential Budi telah dicuri dan attacker sedang mengambil data finance.”

### Tugas

Bedah kalimat tersebut.

**D1.** Bagian mana yang merupakan fact.

**D2.** Bagian mana yang merupakan inference.

**D3.** Bagian mana yang merupakan hypothesis.

**D4.** Evidence apa yang belum ada tetapi dibutuhkan sebelum conclusion tersebut dianggap kuat.

**D5.** Tuliskan ulang conclusion tersebut menjadi **professional preliminary assessment** yang lebih disiplin.

Gunakan gaya investigator.

Bukan gaya berita.

Bukan gaya menuduh.

---

# BAGIAN 6
## ALTERNATIVE EXPLANATION DRILL

Kasus:

> Sebuah akun employee digunakan pada dua workstation dalam rentang waktu lima menit.
>
> Kedua workstation berada dalam jaringan perusahaan.
>
> Employee mengatakan hanya menggunakan satu workstation.
>
> Tidak terdapat bukti langsung tentang malware pada kedua endpoint.

### Tugas

Buat **5 hypothesis**.

Gunakan format:

```text
H1:
H2:
H3:
H4:
H5:
```

Minimal:

**1 innocent explanation**  
**1 technical explanation**  
**1 human/process explanation**  
**1 malicious explanation**  
**1 explanation yang menurutmu paling mudah terlewatkan**

Setelah itu:

**D6.** Tuliskan evidence yang paling bisa membedakan kelima hypothesis tersebut.

Ini latihan untuk melawan **premature closure**.

Jangan membuat semua hypothesis versi yang sama dengan nama berbeda.

---

# BAGIAN 7
## QUESTIONING DRILL 2

Seorang employee berkata:

> “Saya melihat seseorang berada di ruang server sekitar pukul 22:00.”

Jangan langsung mengejar identitas pelaku.

Susun **8 pertanyaan investigative**.

Urutkan dari:

**open-ended → chronology → sensory detail → identification → corroboration**

Hindari pertanyaan yang memasukkan jawaban.

Hindari juga kalimat yang membuat saksi merasa investigator sudah menentukan pelakunya.

Contoh struktur:

```text
1.
2.
3.
4.
5.
6.
7.
8.
```

Setelah itu pilih **2 pertanyaan buatanmu yang paling berisiko leading**, lalu perbaiki.

---

# BAGIAN 8
## ADVERSARY THINKING 2

Sekarang kita masuk lebih dalam.

Skenario:

> Seorang attacker ingin memperoleh akses ke akun internal perusahaan.
>
> Ia mengetahui sebagian employee menggunakan helpdesk untuk password reset.
>
> Ia tidak mengetahui prosedur internal secara lengkap.
>
> Ia tidak memiliki akses fisik ke kantor.
>
> Ia ingin mengurangi kemungkinan terdeteksi.

Gunakan pola:

**Goal → Knowledge → Constraint → Opportunity → Decision → Risk → Adaptation**

### Tugas

**F1. Goal**

Apa outcome yang sebenarnya dicari attacker.

**F2. Knowledge**

Apa yang attacker ketahui.

**F3. Unknowns**

Apa yang attacker belum ketahui.

**F4. Constraints**

Minimal 5 batasan yang dihadapi attacker.

**F5. Opportunity**

Bagian mana dari proses perusahaan yang mungkin menarik bagi attacker.

**F6. Decision**

Mengapa attacker mungkin memilih jalur tersebut.

**F7. Risk**

Apa risiko bagi attacker jika percobaan gagal.

**F8. Adaptation**

Apa yang mungkin attacker ubah setelah menemukan bahwa strategi pertama tidak berhasil.

**F9. Mistake**

Sebutkan minimal 3 kesalahan yang secara realistis dapat membuat aktivitas attacker meninggalkan jejak.

Tetap berada pada level analytical thinking. Tidak perlu membuat instruksi operasional untuk melakukan serangan.

---

# BAGIAN 9
## MEMORY DRILL 2

Baca blok ini **sekali**.

Jangan dicatat.

```text
Subject: Damar
Host: OPS-WS-113
IP: 10.30.18.113
Login: 06:52
Location: 2nd Floor
Badge: 2714
Department: Operations
Event: USB device connected
File: report_q3.xlsx
```

Sekarang **jangan kembali melihat blok di atas**.

Lanjutkan langsung ke Bagian 10.

---

# BAGIAN 10
## SOURCE CORRELATION

### Source A

> Employee mengatakan datang pukul 07:00 dan langsung menuju meja kerja.

### Source B

```text
06:52 — Main Entrance — Damar
06:55 — 2nd Floor — Damar
07:01 — OPS-WS-113 — Damar
```

### Source C

> Coworker mengatakan Damar sudah berada di lantai dua sebelum pukul 07:00.

### Tugas

**H1.** Apa yang konsisten.

**H2.** Apa yang tampak tidak konsisten.

**H3.** Apakah contradiction benar-benar ada.

**H4.** Pisahkan statement employee dari objective evidence.

**H5.** Buat preliminary assessment.

Jangan menggunakan kata:

> bohong  
> pasti  
> malicious

kecuali evidence memang mendukungnya.

---

# BAGIAN 11
## MEMORY RECALL

Sekarang tanpa melihat kembali Memory Block di Bagian 9, tuliskan:

**G1. Subject**

**G2. Host**

**G3. IP**

**G4. Login**

**G5. Location**

**G6. Badge**

**G7. Department**

**G8. Event**

**G9. File**

Perhatikan **angka, kode, dan istilah**, bukan sekadar gambaran umum.

---

# BAGIAN 12
## INTEGRATED ANALYST CASE

Ini bagian utama Day 2.

Baca pelan.

> Pada pukul 18:31, akun `finance01` login ke `FIN-WS-044`.
>
> Pada pukul 18:34, akun tersebut membuka folder `Payroll`.
>
> Pada pukul 18:36, sebuah file bernama `employee_salary.xlsx` dibuka.
>
> Pada pukul 18:39, akun yang sama melakukan login ke `FIN-WS-091`.
>
> Pada pukul 18:41, file yang sama dibuka kembali.
>
> Employee pemilik akun mengatakan bahwa ia sudah pulang pada pukul 17:10.
>
> Supervisor mengatakan pekerjaan payroll hari itu sudah selesai pukul 16:45.
>
> IT mencatat bahwa `FIN-WS-091` biasanya digunakan oleh anggota tim IT.
>
> Tidak ada evidence yang diberikan mengenai malware.
>
> Tidak ada evidence yang diberikan mengenai credential theft.
>
> Tidak ada rekaman CCTV yang dimasukkan ke dalam case.

Sekarang jangan langsung menyimpulkan.

Gunakan struktur:

### I1. FACTS

### I2. OBSERVATIONS

### I3. ANOMALIES

### I4. SOURCE CONTRADICTIONS

### I5. INFERENCES

### I6. HYPOTHESES

Minimal 4.

### I7. INNOCENT EXPLANATION

Minimal 1.

### I8. MALICIOUS EXPLANATION

Minimal 1.

### I9. INFORMATION GAPS

Minimal 7.

### I10. PRIORITY EVIDENCE

Pilih 5 evidence dan urutkan.

### I11. CURRENT ASSESSMENT

Tulis 3 sampai 5 kalimat.

### I12. CONFIDENCE

Pilih:

**Low / Medium / High**

Lalu jelaskan **confidence terhadap assessment**, bukan confidence terhadap perasaanmu.

---

# BAGIAN 13
## MINI RAPID FIRE

Jawab cepat. Jangan membuat penjelasan panjang.

### J1

“Login pukul 02:00.”

Kategori.

### J2

“Login pukul 02:00 berarti employee melakukan tindakan mencurigakan.”

Kategori.

### J3

“Employee mungkin sedang melakukan pekerjaan darurat.”

Kategori.

### J4

“File tersebut pasti malware.”

Kategori.

### J5

“Akses terjadi dari workstation yang berbeda dari workstation biasanya.”

Kategori.

### J6

“Perlu diperiksa apakah workstation tersebut memang berada dalam lokasi yang dapat diakses employee.”

Kategori.

Di bagian ini saya ingin melihat apakah setelah Day 1 kamu mulai lebih cepat membedakan **fact, inference, dan hypothesis**.

---

# FORMAT PENGIRIMAN

Gunakan format:

```text
DAY 2

Durasi:
Waktu mulai:
Waktu selesai:

A1:
A2:
A3:
A4:
A5:
A6:
A7:
A8:

B1:
B2:
B3:
B4:
B5:

C1:
C2:
C3:
C4:
C5:
C6:
C7:

D1:
D2:
D3:
D4:
D5:
D6:

E1:
E2:
E3:
E4:
E5:

F1:
F2:
F3:
F4:
F5:
F6:
F7:
F8:
F9:

G1:
G2:
G3:
G4:
G5:
G6:
G7:
G8:
G9:

H1:
H2:
H3:
H4:
H5:

I1:
I2:
I3:
I4:
I5:
I6:
I7:
I8:
I9:
I10:
I11:
I12:

J1:
J2:
J3:
J4:
J5:
J6:
```
Jadi jangan cuma mendapatkan angka **70/100**, lalu bingung sebenarnya harus memperbaiki apa. Kita akan bedah jawabannya sampai kelihatan bentuk reasoning yang lebih tajam.
