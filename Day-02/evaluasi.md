Baik. Saya **ulang evaluasi Day 2 dengan durasi 1 jam 23 menit, termasuk membaca dan mengerjakan**.

Karena kamu juga bilang banyak istilah Inggris belum dipahami, saya tidak akan menganggap seluruh tambahan waktu itu sebagai masalah speed murni. Sebagian waktu memang habis untuk memahami instruksi. Namun tetap, **83 menit berarti tempo kerjamu masih cukup lambat dibanding target latihan 45 sampai 65 menit**.

# DAY 2, REVISI FINAL

## **58/100 | PASS WITH REMINDER**

**Day 1: 68/100**
**Day 2: 58/100**

Penurunan ini terutama datang dari tiga hal:

**1. Durasi 83 menit**
**2. Memory masih lemah**
**3. Banyak reasoning berubah dari evidence menjadi assumption terlalu cepat**

Tetapi ada satu hal yang justru membaik cukup jelas:

> **Kamu sudah lebih paham membedakan fact, inference, dan hypothesis.**

Jadi ini bukan kemunduran keseluruhan. Lebih tepatnya, Day 2 membuka kelemahan yang lebih dalam.

---

# 1. SPEED

Durasi:

## **1 jam 23 menit = 83 menit**

Target latihan yang saya tetapkan:

**45 sampai 65 menit**

Berarti kamu sekitar **18 menit melewati batas atas**.

Tetapi konteksnya penting. Kamu mengatakan banyak vocabulary Inggris belum kamu pahami. Itu jelas menambah cognitive load.

Jadi saya beri:

### **Speed: 52/100**

Bukan 30 atau 40, karena kamu tetap menyelesaikan hampir seluruh latihan.

Dan saya tidak ingin memaksa kamu ngebut dulu.

Urutan training kita sekarang lebih sehat:

> **Pahami → akurat → baru cepat.**

---

# 2. A, FACT / INFERENCE / HYPOTHESIS

Ini bagian terbaikmu.

Kamu dapat:

**8/8 benar.**

### **A: 95/100**

Kamu sudah menangkap:

**Fact** = informasi yang diberikan
**Inference** = interpretasi
**Hypothesis** = kemungkinan yang perlu diuji

Ini fondasi penting.

Untuk bagian “pernyataan paling berbahaya”, jawaban idealnya:

> **A4 dan A8 paling berbahaya karena keduanya berupa dugaan/kesimpulan yang mudah diperlakukan sebagai fakta apabila investigator tidak disiplin. A4 menyatakan employee sengaja menyembunyikan aktivitas tanpa bukti, sedangkan A8 menyatakan aktivitas tidak sah tanpa verifikasi.**

Jadi sebenarnya kamu sudah mengarah ke jawaban yang benar. Kamu cuma belum tahu **format berpikir yang diminta**.

---

# 3. B, PRECISION

Kamu berhasil menemukan semua perubahan:

> 014 → 041
> 41 → 14
> . → _
> 2026 → 2025
> 42 → 24

Itu bagus.

Masalah ada di dampaknya.

Kamu menjawab:

> “bisa salah input data”

Terlalu dangkal untuk investigator.

### Seharusnya kamu menjawab:

> **Satu karakter yang salah dapat membuat evidence dikaitkan kepada objek yang salah. Misalnya IP yang tertukar dapat membuat aktivitas dikaitkan dengan workstation berbeda, username yang salah dapat menyebabkan salah attribution, dan timestamp yang salah dapat mengubah chronology kejadian.**

Nah.

Yang kita cari bukan sekadar:

> “salah input”

tetapi:

> **kesalahan kecil → correlation salah → attribution salah → assessment salah.**

### **B: 70/100**

---

# 4. C, EVIDENCE TRACE

Ini bagian yang memperlihatkan kelemahanmu paling jelas.

Kamu sudah menemukan anomaly, tetapi kadang langsung memberinya makna.

Contoh:

> “budget internal diakses, padahal itu menggunakan privilege tinggi”

Masalahnya:

**Tidak pernah disebut bahwa file itu membutuhkan privilege tinggi.**

Itu kamu tambahkan sendiri.

### Seharusnya:

> **Anomaly 1:** account Budi melakukan login ke FIN-WS-067 setelah sebelumnya login di FIN-WS-021.
> **Anomaly 2:** file yang sama diakses kembali setelah login dari workstation kedua.

Itu evidence-based.

Sedangkan:

> “Budi melakukan login anomaly karena...”

sudah masuk interpretation.

### C: **55/100**

---

# 5. D, DANGEROUS CONCLUSION

Kamu cukup dekat.

Yang perlu dikoreksi adalah klasifikasinya.

Kalimat:

> “Budi login di dua workstation dalam waktu yang hampir berdekatan.”

### Seharusnya:

**Fact / Observation**

Kalimat:

> “credential Budi telah dicuri.”

### Seharusnya:

**Hypothesis**

Kalimat:

> “attacker sedang mengambil data finance.”

### Seharusnya:

**Hypothesis**

Dan conclusion profesional yang lebih baik:

> **“Terdapat aktivitas login yang tidak biasa pada akun Budi karena akun tersebut tercatat digunakan pada dua workstation dalam waktu yang berdekatan. Aktivitas ini perlu diverifikasi untuk menentukan apakah penggunaan tersebut sah, merupakan kesalahan operasional, atau menunjukkan penggunaan akun oleh pihak lain. Saat ini belum terdapat evidence yang cukup untuk menyimpulkan credential theft atau malicious activity.”**

### D: **61/100**

---

# 6. F, ADVERSARY THINKING

Kamu sudah membaik dibanding Day 1.

Kamu mulai memahami:

> attacker punya constraint
> helpdesk merupakan opportunity
> risiko deteksi penting

Itu bagus.

Tetapi:

> “membangun helpdesk bayangan”

terlalu spesifik. Tidak ada evidence untuk itu.

Kamu juga masih sesekali bergeser dari:

**cara attacker berpikir**

menjadi:

**cara defender memperbaiki sistem**

### Contoh jawaban yang lebih bagus:

> **Goal:** mendapatkan akses ke account internal.
> **Knowledge:** tahu bahwa password reset dapat melibatkan helpdesk.
> **Constraint:** tidak mengetahui prosedur internal lengkap, tidak punya akses fisik, tidak tahu siapa petugas helpdesk, dan berisiko terdeteksi.
> **Opportunity:** proses reset password.
> **Decision:** memilih jalur yang tampaknya membutuhkan effort lebih rendah daripada menyerang sistem secara langsung.
> **Risk:** gagal, terdeteksi, atau meninggalkan authentication logs.
> **Adaptation:** mengubah pendekatan setelah prosedur pertama tidak berhasil.

### F: **60/100**

Ada kemajuan.

---

# 7. G, MEMORY

Masih yang paling lemah.

Memory asli:

> Damar
> OPS-WS-113
> 10.30.18.113
> 06:52
> 2nd Floor
> 2714
> Operations
> USB device connected
> report_q3.xlsx

Jawabanmu hanya tepat di:

**Damar**
**OPS-WS-113**
**2nd Floor**
**Operations**

Sedangkan:

**IP** salah
**Login time** hilang
**Badge** hilang
**Event** hilang
**File** hilang

### **G: 45/100**

Ini tetap menjadi **priority training**.

Kamu punya kecenderungan mengingat:

> **kategori besar**

tetapi kehilangan:

> **angka + identifier + event spesifik**

Ini perlu kita hajar pelan-pelan.

---

# 8. H, SOURCE CORRELATION

Bagian ini sebenarnya membuatmu melakukan kesalahan yang sama seperti Day 1:

> menemukan sesuatu yang terlihat berbeda → langsung menyebut contradiction.

Padahal:

Employee:

> datang sekitar 07:00

Badge:

> 06:52

Coworker:

> sebelum 07:00

Semua itu justru cukup konsisten.

### Seharusnya:

> **Tidak terdapat contradiction besar. Employee mengatakan datang sekitar pukul 07:00, sementara badge menunjukkan 06:52. Pernyataan coworker bahwa Damar sudah berada di lantai dua sebelum pukul 07:00 juga konsisten dengan system record.**

Nah.

Ini penting.

**Perbedaan ≠ contradiction.**

Kalau A mengatakan:

> “sekitar jam 7”

dan system menunjukkan:

> 06:52

itu belum contradiction.

### H: **50/100**

---

# 9. I, INTEGRATED CASE

Ini bagian paling banyak vocabulary yang membuatmu tersandung.

Jadi saya tidak akan cuma bilang “salah”.

Saya jelaskan istilahnya dulu.

### INFORMATION GAP

**Hal penting yang belum kita ketahui.**

Dalam kasus itu misalnya:

> siapa yang benar-benar menggunakan FIN-WS-091
> source IP login kedua
> apakah finance01 berhak menggunakan FIN-WS-091
> apakah IT memang melakukan administrative activity
> apakah employee benar-benar meninggalkan kantor
> apa aktivitas yang dilakukan pada file salary

Itulah information gaps.

---

### INNOCENT EXPLANATION

Artinya:

> **kemungkinan yang tidak melibatkan tindakan jahat.**

Contoh:

> employee ternyata masih bekerja setelah 17:10.

Atau:

> IT melakukan pekerjaan administratif yang sah menggunakan akses tersebut.

---

### MALICIOUS EXPLANATION

Artinya:

> **kemungkinan yang melibatkan tindakan jahat/tidak sah.**

Contoh:

> pihak lain menggunakan account finance01 tanpa izin untuk mengakses payroll.

Tidak perlu langsung mengatakan:

> “attacker adalah tim IT.”

Itu tuduhan terlalu spesifik.

---

### CURRENT ASSESSMENT

Artinya:

> **penilaian sementara berdasarkan evidence yang sudah tersedia sekarang.**

Contoh:

> **“Aktivitas finance01 tergolong anomalous karena digunakan setelah employee menyatakan telah pulang dan kemudian digunakan pada workstation yang biasanya dipakai oleh tim IT. Pengaksesan ulang file salary meningkatkan kebutuhan untuk melakukan verifikasi. Namun evidence saat ini belum cukup untuk menentukan apakah aktivitas tersebut merupakan pekerjaan yang sah, penggunaan akun oleh pihak lain, atau explanation lain.”**

---

### CONFIDENCE

Artinya:

> **seberapa kuat assessment tersebut didukung evidence.**

Untuk kasus tersebut:

### **LOW**

Karena anomaly-nya nyata, tetapi penyebabnya belum terbukti.

---

### I: **48/100**

Namun saya tidak menganggap ini sebagai kegagalan murni reasoning.

Sebagian besar masalahmu di sini adalah:

> **belum menguasai vocabulary analytical.**

Jadi saya akan masukkan istilah tersebut ke latihan berikutnya dalam Bahasa Indonesia terlebih dahulu.

---

# 10. J, RAPID FIRE

Jawabanmu:

**J1 Fact ✅**

**J2 Hypothesis ✅**

**J3 Hypothesis ✅**

**J4 Hypothesis ✅**

**J5 Kesimpulan ❌**

Seharusnya:

> **Fact / Observation**

**J6 Kesimpulan ❌**

Seharusnya:

> **Recommendation / verification step**

Jadi:

### **4/6 benar**

### J: **67/100**

---

# REVISI NILAI PER SKILL

| Skill              |  Day 2 |
| ------------------ | -----: |
| Fact vs Inference  | **95** |
| Precision          | **70** |
| Observation        | **60** |
| Reasoning          | **64** |
| Memory             | **45** |
| Communication      | **58** |
| Adversary Thinking | **60** |
| Assumption Control | **50** |
| Source Correlation | **50** |
| Speed              | **52** |
| Mental Discipline  | **72** |

## Nilai keseluruhan:

# **58/100**

### STATUS:

## **PASS WITH REMINDER**

---

# YANG BERUBAH DARI DAY 1

Day 1 kamu:

> cukup cepat, tetapi sering kehilangan detail.

Day 2:

> **kamu sudah lebih paham struktur reasoning, tetapi ketika kasus makin kompleks, assumption mulai masuk lagi.**

Jadi ada progress.

Yang paling penting:

## **Fact vs inference sudah mulai masuk ke kepala.**

Sekarang kita perlu membuat kemampuan itu bertahan saat kasus lebih rumit.

---

# ERROR PROFILE TERKINI

### 🔴 PRIORITAS 1

**Memory exact detail**

Angka, timestamp, identifier, nama file.

### 🔴 PRIORITAS 2

**Assumption control**

Jangan mengubah:

> “file dibuka”

menjadi:

> “file berisi malware”.

### 🟠 PRIORITAS 3

**Observation discipline**

Deskripsikan apa yang terjadi tanpa menambahkan makna.

### 🟠 PRIORITAS 4

**Vocabulary analytical**

Information gap, current assessment, innocent explanation, confidence, corroboration, attribution, dan seterusnya.

### 🟡 PRIORITAS 5

**Speed**

Belum perlu dipaksa.

Saya lebih memilih kamu menghabiskan **70 menit dengan accuracy naik** daripada turun menjadi 45 menit tetapi evidence-nya berubah-ubah.

---

# FORMAT EVALUASI MULAI SEKARANG

Saya pegang permintaanmu tadi.

Untuk jawaban yang kurang tepat, evaluasinya akan selalu punya pola:

> **Jawabanmu:**
> “budget internal menggunakan privilege tinggi”

> **Masalah:**
> Evidence tidak pernah menyebut privilege tinggi.

> **Seharusnya kamu menjawab ini:**
> **“File budget_internal.xlsx kembali diakses setelah account Budi login ke FIN-WS-067.”**

> **Kenapa:**
> Itu mempertahankan fakta yang benar-benar diberikan tanpa menambahkan asumsi.

Jadi kamu akan selalu melihat **versi jawaban yang menurut saya lebih baik**, bukan hanya angka nilai.

Dan mulai **Day 3**, saya akan mengurangi kalimat Inggris yang tidak perlu. Istilah profesional tetap akan dipakai, tetapi langsung saya kasih arti Indonesianya. Tujuannya supaya kamu belajar **investigation**, bukan sibuk menerjemahkan setiap paragraf.

**DAY 2: SELESAI. 58/100. PASS WITH REMINDER.**
