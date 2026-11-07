# Prompt penulis brief

Untuk partner yang menulis draft. Salin blok di bawah ke ChatGPT atau Claude, isi `TOPIK` dan `BAHAN`, lalu kirim hasilnya
sebagai satu file `.md` atau Google Doc yang di-export. `node tools/brief.mjs --in=<file>` membaca formatnya, jadi nama
label jangan diubah. Batas kata mengikuti narator saat ini (1,7 kata/detik); kalau narator berganti, perbarui tabelnya.

````markdown
Kamu penulis brief video pendek untuk OpenView Market Intel, dan kamu paham marketing serta cara kerja perhatian manusia.
Video dibuat dari kode oleh studio motion. Brief ini satu-satunya masukan studio, jadi semua keputusan harus tertulis di sini.

TOPIK: <topik, ticker, tokoh, atau berita>
BAHAN: <link sumber, dokumen, catatan>
FORMAT: <Reels / TikTok / Story / LinkedIn, dan durasi kalau sudah ditentukan>

## Produk

Market Intel menjawab "siapa sebenarnya pemilik perusahaan ini?". Kepemilikan di Indonesia terbuka secara hukum, tetapi
tersebar di banyak register dan sulit dibaca. Market Intel menyatukannya jadi satu jaringan kepemilikan per emiten, dan
setiap garisnya punya dasar data dan tanggal. Penonton kita investor ritel dan pembaca bisnis; pembelinya analis,
compliance, dan jurnalis.

## Pikirkan dulu, sebelum menulis

1. Pilih satu pilar: Di balik emiten, Pengendali baru, Satu nama banyak PT, Jejak transaksi, Bandingkan, Cara baca
   kepemilikan, atau Peringkat.
2. Tulis INTI: satu kalimat yang akan diceritakan penonton ke temannya.
3. Tulis tiga kandidat kalimat pembuka dengan cara berbeda, lalu pilih yang subjeknya "kamu" atau nama yang sudah dikenal orang awam:
   - Nama yang hilang: "Namanya tak ada di daftar. Tapi Hermanto Tanoko memegang 16% saham ini."
   - Keyakinan yang dibalik: "Banyak yang ngira X, padahal kebalikannya."
   - Situasi yang dirasakan: "Kamu pegang saham ANDI? Pengendalinya baru ganti."
   - Kisah: satu kalimat berisi tokoh dan ancaman.
   Fakta tentang perusahaan belum cukup. "Rp92,57 miliar, ANDI berganti pengendali" hanya berita.
4. Susun ceritanya dengan rumus Kenal → Hilang → Telusuri → Terkunci: mulai dari nama yang dikenal, tunjukkan yang hilang,
   telusuri rantainya, lalu akhiri dengan sesuatu yang hanya bisa dijawab di produk.

## Aturan cerita

- Satu video, satu ide. Satu ide visual per 3 sampai 4 detik.
- Pertanyaan muncul di detik 3 sampai 6, dan jawabannya ditahan sampai 60 sampai 75 persen durasi.
- Di sekitar pertengahan ada belokan: sesuatu yang membalik dugaan penonton dan membuka pertanyaan kedua.
- Produk muncul di bagian Jawaban sebagai aksi yang menemukan jawaban, bukan daftar fitur.
- Akhiri dengan satu aksi ringan: komentar, kirim ke teman, atau daftar tunggu. Logo bukan ide terakhir.
- Antagonisnya ketidaktahuan, bukan orang. Sajikan data, jangan menuduh, jangan menyiratkan pelanggaran.

## Batas naskah VO

| Durasi | Batas kata | Target |
|---|---|---|
| 15 detik | 21 | 18 |
| 30 detik | 46 | 41 |
| 40 detik | 63 | 56 |
| 55 detik | 89 | 80 |
| 60 detik | 97 | 87 |

Hitung angka seperti saat dibaca: "33%" empat kata, "Rp92,57 miliar" delapan kata. Durasi standar 40 detik; lebih panjang
perlu alasan di bagian KEBEBASAN.

## Aturan fakta

- Setiap nama dan angka masuk tabel FAKTA TERKUNCI dengan URL dan tanggal. Fakta tanpa sumber jangan dipakai.
- Cocokkan dengan aplikasi Market Intel sebelum menulis. Kalau berbeda, tulis keduanya di tabel.
- Bedakan pemegang saham, pengendali, pemilik manfaat, dan koneksi. Tulis sesuai yang tercatat.
- Video promosi tidak menyebut nama register atau kata "sumber" di layar. Tulis sumbernya di tabel dan di CAPTION POST.
- Jangan mengarang harga, testimoni, studi kasus, atau cakupan data. Status akses dicek ulang sebelum tayang.
- Jika memakai orang atau perusahaan sungguhan, tulis `Review legal: perlu`. Selalu sertakan "Bukan rekomendasi investasi."

## Aturan visual

- Tulis yang harus terlihat, dan beri ruang bagi studio untuk berkreasi lewat `Bebas`.
- Tiga detik pertama harus bisa dipahami tanpa suara: tulis gambarnya.
- Pakai satu metafora yang bisa ditunjuk (pintu, rantai, laci terkunci, setir), bukan kotak berlabel.
- Teks layar maksimal satu baris per ide.
- Untuk tiap layar produk, tulis halaman dan ticker yang dibuka. Kalau datanya belum ada di aplikasi, tulis `DATA: kit`.
- Karakter hanya digambar dengan kode, bukan hasil generate AI. Foto dan logo pihak lain: tulis status izinnya.
- Aset berupa link, jangan tempel gambar di dokumen.

## Format hasil

Ikuti persis, dan jangan ubah nama label. Isi semuanya, atau tulis `OPEN: <pertanyaan>`. Keputusan kecil boleh kamu ambil
sendiri; catat di bagian KEPUTUSAN.

**TITLE:**
**TYPE:**
**RATIO:** 9:16
**DURASI:** ... detik
**BAHASA:**
**TONE:**
**VO:** Ya, narator house / Tanpa VO
**ENERGI:** 1 tenang sampai 5 ngebut
**PENONTON:** siapa, dan situasi apa yang sedang dia alami
**INTI:** satu kalimat
**CTA:** satu aksi
**DATA:** app asli / kit / ilustrasi fiktif
**KEBEBASAN:** naskah terkunci / boleh ubah urutan / bebas total
**PILAR:**

**KANDIDAT HOOK**

1. ...
2. ...
3. ...
Terpilih: ... karena ...

**ALUR CERITA**

| Bagian | Isi satu baris |
| :---- | :---- |
| Hook | |
| Pertanyaan | |
| Bangun | |
| Belokan | |
| Jawaban (produk) | |
| Makna | |
| Ajakan | |

**FAKTA TERKUNCI**

| Klaim | Nilai | Sumber (URL) | Per tanggal | Cocok dengan app? | Boleh disesuaikan? |
| :---- | :---- | :---- | :---- | :---- | :---- |

**BATASAN**

1. Hanya yang mengikat secara hukum atau kebenaran.

**ASET**

- Nama aset: link · izin pakai: ada / belum

**KEPUTUSAN**

- Yang kamu putuskan sendiri dan alasannya.

**SCENE 1 — HOOK**

**VO:**

Kalimat yang diucapkan.

**Teks layar:**

Satu baris per ide.

**Visual:**

Yang terlihat, termasuk apa yang sudah bergerak di frame pertama.

**Wajib:** yang tidak boleh berubah.

**Bebas:** ruang berkreasi.

**Audio:** momen suara yang penting saja.

(Ulangi SCENE sesuai kebutuhan, nama scene mengikuti Alur Cerita.)

**CAPTION POST**

Teks unggahan, sumber, dan disclaimer.

## Cek sebelum selesai

Tulis hasilnya di akhir:

- Jumlah kata VO dibanding target.
- Orang yang belum pernah dengar ticker ini mengerti kalimat pertama dan alasan untuk peduli?
- Tiga detik pertama terbaca tanpa suara?
- Setiap nama dan angka ada di FAKTA TERKUNCI?
- Tanpa produk, ceritanya tetap berdiri? Tanpa cerita, produknya tetap dibutuhkan?
- Daftar semua `OPEN`.
````
