# DAY 3

## CHRONOLOGY • SOURCE EVALUATION • CONTRADICTION • HYPOTHESIS CONTROL

Hari ini kita masuk ke wilayah yang sedikit lebih “abu-abu”. Data tidak akan selalu terang-terangan bilang mana yang benar. Kamu harus **menyusun urutan kejadian, membedakan fakta dari cerita, lalu menentukan apa yang layak dipercaya sementara**.

Fokus utama Day 3:

**Chronology** = urutan kejadian
**Source evaluation** = menilai kualitas sumber
**Contradiction** = pertentangan informasi
**Corroboration** = informasi lain yang memperkuat sumber
**Attribution** = menghubungkan aktivitas kepada pihak tertentu
**Premature closure** = terlalu cepat merasa sudah menemukan jawaban

Semua ini masih berdiri di atas pola yang kita gunakan sebelumnya:

**Observe → Question → Hypothesize → Investigate → Verify → Assess.**

Untuk hari ini, **jangan kejar kecepatan dulu**. Target nyaman sekitar **55 sampai 75 menit**, termasuk membaca. Kamu cukup mencatat waktu total seperti dua hari sebelumnya.

---

# BAGIAN 1

## MICRO THEORY: CHRONOLOGY

Investigator sering tidak kekurangan data.

Yang berantakan justru **urutan datanya**.

Contoh:

```text
18:14  login
18:27  logout
18:17  file dibuka
18:22  USB terhubung
18:15  browser dibuka
```

Kalau kamu membaca sesuai urutan tulisan, otak gampang membangun cerita yang salah.

### Prinsip Day 3

> **Jangan baca data sebagai paragraf. Baca sebagai timeline.**

Urutan yang benar:

```text
18:14 login
18:15 browser dibuka
18:17 file dibuka
18:22 USB terhubung
18:27 logout
```

Chronology membantu kita membedakan:

> **apa yang terjadi dulu**

dengan:

> **apa yang kita kira terjadi dulu**

---

# BAGIAN 2

## CHRONOLOGY DRILL

Susun event berikut dari yang paling awal sampai paling akhir.

```text
A. 14:18 — file payroll.xlsx dibuka
B. 14:11 — user login
C. 14:23 — user logout
D. 14:16 — removable media terdeteksi
E. 14:13 — browser dibuka
F. 14:20 — file payroll.xlsx disalin
G. 14:27 — workstation dikunci
```

### Tugas

**A1.** Urutkan A sampai G.

**A2.** Event mana yang paling penting untuk menentukan apakah aktivitas terjadi dalam satu session.

**A3.** Buat satu kalimat chronology dalam Bahasa Indonesia.

### Contoh bentuk yang bagus

> “User login pada 14:11, kemudian browser dibuka pada 14:13, removable media terdeteksi pada 14:16, file payroll dibuka pada 14:18, file disalin pada 14:20, user logout pada 14:23, lalu workstation dikunci pada 14:27.”

Jangan hanya menyusun angka. **Bangun alurnya.**

---

# BAGIAN 3

## SOURCE EVALUATION

Sekarang kita bedakan empat hal:

### Sumber langsung

Contoh system log yang mencatat event.

### Sumber observasional

Contoh orang yang melihat kejadian.

### Pernyataan pihak terlibat

Contoh employee menjelaskan apa yang ia lakukan.

### Informasi sekunder

Contoh orang lain menceritakan apa yang ia dengar.

Tidak berarti:

> system log selalu benar

atau:

> manusia selalu bohong.

Yang kita nilai adalah:

**reliability, consistency, proximity, corroboration**

### Vocabulary

**Reliability** = seberapa dapat diandalkan sumber.
**Consistency** = apakah informasinya selaras dengan data lain.
**Proximity** = seberapa dekat sumber dengan kejadian.
**Corroboration** = apakah ada evidence lain yang mendukung.

---

# BAGIAN 4

## SOURCE COMPARISON

Kasus:

### Source A

Employee:

> “Saya keluar kantor sekitar pukul 18:00.”

### Source B

Badge system:

```text
17:52 — Main Exit
```

### Source C

Coworker:

> “Saya melihat dia masih di meja sekitar pukul 17:45.”

### Source D

VPN log:

```text
18:07 — employee01 authenticated remotely
```

### Tugas

**B1.** Mana yang merupakan direct system evidence.

**B2.** Mana yang merupakan human statement.

**B3.** Apa yang konsisten.

**B4.** Apa yang tampak tidak konsisten.

**B5.** Apakah Source A otomatis salah.

**B6.** Apa kemungkinan innocent explanation.

**B7.** Evidence tambahan apa yang paling membantu menjelaskan Source D.

---

# BAGIAN 5

## CONTRADICTION ATAU BUKAN

Ini penting karena Day 2 kamu sempat menganggap **perbedaan kecil sebagai contradiction**.

Tentukan:

**C = contradiction**
**N = not a contradiction**

### C1

Employee:

> “Saya tiba sekitar jam 8.”

Badge:

> 07:52

### C2

Employee:

> “Saya tidak pernah menggunakan FIN-WS-071.”

Log:

> 09:14 — employee01 logged into FIN-WS-071

### C3

Coworker:

> “Dia keluar sebelum jam 6.”

Badge:

> 17:53 exit

### C4

Employee:

> “Saya membuka file itu pagi hari.”

Log:

> 08:14 file access

### C5

Employee:

> “Saya bekerja sampai kira-kira jam 5.”

Log:

> 16:58 logout

### C6

Employee:

> “Saya berada di lantai tiga.”

Badge:

> 15:12 — 3rd Floor

Setelah memberi C atau N, jelaskan **satu kalimat alasan**.

---

# BAGIAN 6

## HYPOTHESIS MATRIX

Skenario:

> Account `user_17` digunakan pada FIN-WS-018 pukul 10:02.
>
> Delapan menit kemudian account yang sama digunakan pada FIN-WS-044.
>
> Kedua workstation berada di lantai berbeda.
>
> Employee mengatakan bahwa ia hanya menggunakan FIN-WS-018.
>
> Belum ada evidence malware.

Kita tidak akan langsung memilih satu jawaban.

Buat tabel sederhana:

| Hypothesis | Evidence yang mendukung | Evidence yang melemahkan |
| ---------- | ----------------------- | ------------------------ |
| H1         |                         |                          |
| H2         |                         |                          |
| H3         |                         |                          |
| H4         |                         |                          |

Gunakan empat hypothesis:

**H1:** employee memang menggunakan workstation kedua secara sah.

**H2:** pihak lain menggunakan account tersebut.

**H3:** aktivitas kedua berasal dari mekanisme remote/session yang sah.

**H4:** ada kesalahan pencatatan atau interpretasi pada log.

### Setelah itu:

**D1.** Hipotesis mana yang paling masuk akal sementara.

**D2.** Mengapa.

**D3.** Evidence apa yang dapat membuatmu mengubah pikiran.

Ini latihan penting.

Investigator yang baik bukan orang yang **selalu benar sejak awal**.

Investigator yang baik adalah orang yang:

> **mau mengubah assessment ketika evidence berubah.**

---

# BAGIAN 7

## MEMORY + DISTRACTION

Sekarang baca sekali:

```text
Subject: Nanda
Host: SEC-WS-204
IP: 10.40.21.204
Login: 09:17
Location: 4th Floor
Badge: 3921
Department: Security
Event: Archive extracted
File: incident_case_14.zip
```

Jangan dihafal dengan cara membaca ulang berkali-kali.

Setelah membaca, **lanjutkan langsung ke Bagian 8**.

Kita akan menguji recall nanti.

---

# BAGIAN 8

## INVESTIGATOR NOTE

Baca case berikut:

> Pada pukul 09:10, seorang supervisor mengatakan bahwa employee “terlihat panik”.
>
> Pada pukul 09:14, employee membuka folder Finance.
>
> Pada pukul 09:17, employee mengirim email kepada supervisor.
>
> Pada pukul 09:20, employee meninggalkan workstation.
>
> Supervisor kemudian mengatakan:
>
> “Saya yakin dia sedang mencoba menghapus sesuatu.”

### Tugas

**E1.** Mana facts.

**E2.** Mana observations.

**E3.** Mana inference.

**E4.** Mana hypothesis.

**E5.** Apa yang belum diketahui.

**E6.** Mengapa “terlihat panik” tidak cukup untuk membuktikan malicious intent.

**E7.** Evidence apa yang perlu diperiksa untuk menguji klaim supervisor.

Kali ini saya ingin kamu **sengaja melawan godaan untuk percaya pada cerita supervisor**.

---

# BAGIAN 9

## COMMUNICATION DRILL: OPEN → NARROW

Seorang saksi berkata:

> “Ada seseorang masuk ke ruangan server.”

Kamu ingin mengetahui chronology tanpa mengarahkan saksi.

Susun **7 pertanyaan**.

Urutannya:

**1. Open-ended**
**2. Waktu**
**3. Lokasi**
**4. Aktivitas**
**5. Ciri orang**
**6. Apa yang terjadi setelahnya**
**7. Corroboration**

Contoh pola:

> “Ceritakan apa yang kamu lihat.”

Setelah itu buat enam pertanyaan berikutnya.

### Larangan

Jangan mulai dengan:

> “Apakah itu Andi?”

Jangan:

> “Dia kan orang IT.”

Jangan:

> “Dia masuk untuk mengambil data.”

Kita belum tahu.

---

# BAGIAN 10

## ADVERSARY THINKING

Kasus:

> Seseorang ingin memperoleh informasi internal perusahaan.
>
> Ia mengetahui bahwa banyak employee menyimpan dokumen kerja di cloud perusahaan.
>
> Ia tidak mengetahui file mana yang paling penting.
>
> Ia tahu bahwa aktivitas dengan volume besar lebih mudah terlihat.
>
> Ia ingin tetap tidak mencolok.

Kita tetap berada pada level analitis, bukan membuat panduan serangan.

### Tugas

**F1. Goal**

Apa tujuan utamanya.

**F2. Knowledge**

Apa yang sudah diketahui.

**F3. Unknowns**

Apa yang belum diketahui.

**F4. Constraint**

Minimal 4 hal yang membatasi.

**F5. Opportunity**

Apa yang menarik perhatian attacker.

**F6. Decision**

Bagian mana yang kemungkinan akan diprioritaskan.

**F7. Detection risk**

Apa yang dapat membuat aktivitasnya terlihat.

**F8. Adaptation**

Bagaimana strategi mungkin berubah setelah mendapati satu pendekatan terlalu terlihat.

**F9. Defensive clue**

Jejak apa yang mungkin membantu investigator mendeteksi pola tersebut.

---

# BAGIAN 11

## MEMORY RECALL

Sekarang tanpa melihat Bagian 7:

**G1. Subject**

**G2. Host**

**G3. IP**

**G4. Login**

**G5. Location**

**G6. Badge**

**G7. Department**

**G8. Event**

**G9. File**

Saya lebih tertarik pada **akurasi exact detail** daripada kelengkapan jawaban.

---

# BAGIAN 12

## FULL CASE: “TIGA CERITA”

Ini kasus utama Day 3.

### System Log

```text
08:42 — user_04 login — OPS-WS-031
08:46 — user_04 access — Operations\Planning
08:51 — removable media connected
08:54 — planning_q4.xlsx opened
08:59 — user_04 logout
```

### Employee Statement

> “Saya datang jam 08:30, bekerja di OPS-WS-031, membuka file planning, lalu pulang dari area kerja sekitar jam 09:00.”

### Supervisor Statement

> “Dia tidak seharusnya membuka file itu karena pekerjaan tersebut sudah selesai kemarin.”

### Coworker Statement

> “Saya melihat dia membawa flash drive ketika masuk ke ruangan.”

### Security Record

```text
08:31 — Employee badge: Main Entrance
08:35 — Employee badge: 3rd Floor
09:06 — Employee badge: Main Exit
```

Sekarang analisis.

### H1. FACTS

Minimal 8.

### H2. OBSERVATIONS

Minimal 5.

### H3. ANOMALIES

Minimal 4.

### H4. SOURCE CONTRADICTIONS

Tentukan mana yang benar-benar contradiction dan mana yang cuma difference.

### H5. HYPOTHESES

Minimal 4.

Harus ada:

**2 innocent/legitimate explanations**

dan

**2 potentially malicious explanations**

### H6. INFORMATION GAPS

Minimal 7.

### H7. PRIORITY EVIDENCE

Pilih 5 dan urutkan.

### H8. CORROBORATION

Evidence apa yang dapat memperkuat statement employee.

Evidence apa yang dapat memperkuat statement coworker.

Evidence apa yang dapat memperkuat statement supervisor.

### H9. CURRENT ASSESSMENT

Tuliskan **3 sampai 5 kalimat**.

Gunakan pola:

> **Saat ini evidence menunjukkan...**
> **Hal yang paling anomalous adalah...**
> **Namun belum dapat dipastikan...**
> **Prioritas verifikasi adalah...**

### H10. CONFIDENCE

Pilih:

**Low / Medium / High**

Lalu jelaskan alasannya.

---

# BAGIAN 13

## PRECISION CHECK

Saya sengaja buat beberapa detail yang mudah tertukar.

Perhatikan:

```text
OPS-WS-031
OPS-WS-013
```

```text
08:42
08:24
```

```text
planning_q4.xlsx
planning_q3.xlsx
```

```text
08:31
08:35
08:51
08:54
08:59
09:06
09:00
09:06
```

### Tugas

**I1.** Mana pasangan identifier yang berbeda.

**I2.** Mana timestamp yang berurutan.

**I3.** Berapa menit antara login dan removable media.

**I4.** Berapa menit antara removable media dan file opening.

**I5.** Berapa menit antara file opening dan logout.

**I6.** Apakah employee mengatakan pulang sekitar 09:00, sementara badge menunjukkan exit 09:06, merupakan contradiction.

**I7.** Jelaskan.

Bagian ini sengaja melatih kelemahan Day 1 dan Day 2:

**angka kecil, chronology, dan exact identifier.**

---

# BAGIAN 14

## MINI ASSESSMENT

Tentukan label terbaik:

**FACT / OBSERVATION / INFERENCE / HYPOTHESIS / INFORMATION GAP / VERIFICATION STEP**

### J1

> “Employee01 login pada 08:42.”

### J2

> “Employee01 melakukan aktivitas mencurigakan.”

### J3

> “Mungkin removable media digunakan untuk menyalin data.”

### J4

> “Kita belum tahu siapa yang membawa removable media.”

### J5

> “Periksa USB history pada workstation.”

### J6

> “File dibuka setelah removable media terhubung.”

### J7

> “Employee sengaja mencuri data.”

---
`
