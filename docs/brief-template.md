# Template draft konten

Salin ke Google Docs, isi, export `.md`. `node tools/brief.mjs --in=<file>` membaca header ini dan mencetak apa yang
masih terbuka. Setiap field ada karena pernah mahal kalau diputuskan belakangan (alasannya di bagian bawah). Versi lengkap
untuk penulis draft, dengan aturan cerita dan fakta: `docs/brief-prompt.md`.

```markdown
**TITLE:** Judul kerja
**TYPE:** Instagram Reels / TikTok / IG Story / LinkedIn
**RATIO:** 9:16
**DURASI:** 55 detik (maksimum)
**BAHASA:** Indonesia
**TONE:** Tenang, kredibel, investigatif
**VO:** Ya, narator house / Tanpa VO
**ENERGI:** 1 tenang … 5 ngebut (tempo gambar, terpisah dari tone)
**PENONTON:** siapa, dan situasi apa yang sedang dia alami
**INTI:** satu kalimat yang akan dia ceritakan ke temannya
**CTA:** satu aksi (komentar kata tertentu / kirim ke teman / daftar tunggu)
**DATA:** app asli (rekaman) / digambar ulang dengan kit / ilustrasi fiktif
**KEBEBASAN:** naskah terkunci / boleh ubah urutan / bebas total

**FAKTA TERKUNCI**

| Klaim | Nilai | Sumber (URL) | Per tanggal | Boleh disesuaikan ke app? |
| :---- | :---- | :---- | :---- | :---- |

**BATASAN** (hanya yang mengikat secara hukum atau kebenaran; preferensi visual masuk ke scene)

1. ...

**ASET** (link Drive atau path file, bukan gambar yang ditempel di dokumen)

- Logo X: <link> · izin pakai: ada / belum

**SCENE 1 — HOOK**

**VO:**

Kalimat yang diucapkan, angka sudah ditulis sebagai kata bila pengucapannya penting.

**Teks layar:**

Maksimal satu baris per ide.

**Wajib:** hal yang tidak boleh berubah di scene ini.

**Bebas:** ruang untuk berkreasi. Ide visual boleh ditulis di sini sebagai saran.

**Audio:** momen suara yang penting saja.
```

## Kenapa tiap field ada

| Field | Biaya kalau kosong (dari log) |
|---|---|
| BAHASA, VO | `mi-demo-40`: bahasa dan ticker berubah setelah take pertama, VO dibayar tiga kali (±2.474 kredit), sesi 190 turn. |
| ENERGI | `satu-persen-58`: draft minta tenang, aturan house minta padat; ditanyakan di tengah pre-production. |
| INTI, PENONTON | Script ditulis dari angka, bukan dari situasi penonton. Hook ronde pertama 6–7 pada 4 dari 5 film terakhir. |
| FAKTA TERKUNCI, kolom terakhir | `andi-55`: "15 koneksi" berbeda dari app; `aspi-55`: dua sumber pemilik manfaat berbeda. Keduanya berhenti menunggu keputusan owner. |
| DATA | Tiga film terakhir memakai kata "wajib screen asli" sementara default studio menggambar ulang dengan kit; keputusannya baru keluar di tengah pre-production. |
| KEBEBASAN, Wajib/Bebas | Scene menulis visual secara literal padahal pesan owner "bebas berkreasi"; agent tidak tahu mana yang boleh diubah. |
| ASET sebagai link | Draft ANDI 192 kB, teksnya hanya 9 kB, sisanya base64. Google Doc privat gagal dibaca (HTTP 401): dua pertanyaan dan menunggu export. |
| CTA | `andi-55` dan `satu-persen-58` berakhir di logo dan URL; referensi yang dipelajari berakhir di permintaan komentar atau kirim ke teman. |

Satu file `.md` di `D:\` cukup. `tools/brief.mjs` memindahkan gambar yang masih tertempel ke `assets/brief/`.
