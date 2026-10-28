# Cherry MotionPlus: Dokumen Kesepakatan

Tanggal: 28 Oktober 2026
Pembuat: Toto Gutomo, S.Pd., Gr., M.Pd., CPSS
Guru SMA Negeri 3 Maliku

Dokumen ini merangkum hasil diskusi perencanaan. **Belum ada kode yang dibangun.** Kode baru dibangun setelah ada perintah eksplisit dari Pak Guru ("Bangun Kode", "Gas kode", atau sejenisnya).

Label status yang dipakai:
- **[DIPUTUSKAN]** sudah disetujui Pak Guru.
- **[USULAN]** saran Claude, belum diputuskan.
- **[BELUM DIPUTUSKAN]** masih perlu dibahas.

---

## 1. Ringkasan proyek

- **Nama:** Cherry MotionPlus [DIPUTUSKAN]
- **Fungsi:** mengubah video biasa menjadi video dengan *auto motion* (teks bergerak, scene, transisi, suara, dan musik).
- **Alur pengguna:** 1. Upload, 2. Pilih gaya, 3. Pencet.
- **Bentuk:** aplikasi Windows yang berjalan offline di laptop [DIPUTUSKAN].
- **Motto pemilihan AI:** gunakan yang terkuat yang masih didukung perangkat [DIPUTUSKAN].
- **Prinsip:** gratis tanpa batas pemakaian, offline, dan video tidak diunggah ke server orang lain.

### Aplikasi referensi

Aplikasi auto motion dari iklan Instagram akun contentscaleup, dijual sekitar Rp99 ribu menurut Pak Guru. Analisis hanya dari **satu tangkapan layar**, jadi bagian teknis di bawah adalah dugaan, bukan hasil pembongkaran kode.

Langkah proses yang terbaca di layar referensi:
1. Membaca video.
2. Mengambil audio.
3. AI mendengarkan dan membuat transkrip.
4. AI melihat wajah dan suasana.
5. AI mengenali footage milik pengguna.
6. AI menyusun motion graphics.
7. AI merancang scene, transisi, suara, dan musik.
8. AI membuat b-roll (gambar pendukung).
9. Menyiapkan pemisah orang dan latar.

Kesimpulan analisis: aplikasi referensi adalah rangkaian langkah otomatis, bukan satu AI tunggal. Inti kekuatannya ada pada "otak penyusun rencana" yang mengubah transkrip dan suasana menjadi rencana motion.

---

## 2. Perangkat dan keputusan platform

| | Xiaomi 13T | Advan Workplus Heritage (laptop) |
|---|---|---|
| Prosesor | Dimensity 8200-Ultra | Ryzen 5 7535HS |
| RAM | 12 GB | 16 GB (DDR5) |
| Penyimpanan | 21,3 GB kosong dari 256 GB | 512 GB SSD |
| Sistem | Android 16 | Windows |

Spesifikasi 13T dari tangkapan layar Pak Guru. Spesifikasi laptop dari hasil pencarian web, **mohon dicek ke laptop**.

**[DIPUTUSKAN]** Aplikasi dibangun untuk **laptop** karena lebih kuat. Aplikasi terpisah, bukan fitur di TeGe Video.

Catatan: versi HP sempat dibahas (AI 4 miliar parameter, 3-5 GB), tetapi tidak dipilih.

---

## 3. Keputusan fitur

### Fitur inti [DIPUTUSKAN]
- Upload satu video.
- Pilih satu gaya.
- Satu tombol Pencet, lalu progres langkah.
- Pratinjau dan ekspor MP4.

### Fitur opsional: semua masuk [DIPUTUSKAN]
1. Edit teks hasil transkrip sebelum diproses.
2. Footage milik Pak Guru sendiri sebagai pengganti b-roll (lewat "Folder Pustaka Saya").
3. Antrean beberapa video.
4. Simpan gaya favorit.
5. Ubah rencana motion sebelum render.

### Ukuran video [DIPUTUSKAN]
Vertikal **dan** horizontal. Konsekuensi: setiap gaya perlu tata letak untuk dua ukuran, jadi pengujian dua kali lipat.

### Dua mode proses [DIPUTUSKAN]
- **Cepat:** AI 4 miliar parameter, pemisah latar di 720p, sekitar 8-12 menit per video 60 detik.
- **Kualitas:** AI 7-8 miliar parameter, 1080p, sekitar 15-20 menit per video 60 detik.

### Stiker [DICORET]
Pak Guru membatalkan pembuatan stiker karena khawatir kecewa dengan hasilnya.

### Menu utama [USULAN, belum dikonfirmasi satu per satu]
1. Beranda: upload video, pilih gaya, tombol Pencet.
2. Proses: daftar langkah AI dan perkiraan waktu.
3. Hasil: pratinjau dan ekspor.
4. Gaya: daftar gaya motion.
5. Pengaturan: mode Cepat atau Kualitas, lokasi simpan, Folder Pustaka Saya.
6. Panduan dan Tentang.

---

## 4. Gaya motion

Delapan gaya diusulkan. **[USULAN]** versi pertama berisi 5 gaya (nomor 1, 2, 3, 4, 8). Pak Guru belum memutuskan daftar akhirnya.

| No | Gaya | Ciri | Masuk versi 1 (usulan) |
|---|---|---|---|
| 1 | Kelas Cerdas | poin penting muncul bergantian, ikon sederhana, warna bersih | ya |
| 2 | Sejarah Klasik | warna sepia, teks ala koran atau lontar, transisi gulungan | ya |
| 3 | Kata Demi Kata | teks menyala mengikuti ucapan (gaya karaoke) | ya |
| 4 | Pop Santai | warna cerah, gerak memantul, kesan fun | ya |
| 5 | Kutipan Tegas | kata besar di belakang orang | menyusul |
| 6 | Berita Kilat | judul di bawah layar dan teks berjalan | menyusul |
| 7 | Sinematik | garis hitam atas-bawah, judul besar, transisi halus | menyusul |
| 8 | Nuansa Kalimantan | motif Dayak sebagai hiasan dan bingkai | ya |

---

## 5. Rencana AI (laptop 16 GB)

Semua dipilih dengan prinsip "terkuat yang masih didukung". Nama dan versi model perlu dicek lagi saat membangun, karena cepat berubah. **Lisensi wajib dicek di halaman resmi tiap model sebelum dipakai.** Rincian sumber ada di `HASIL_PINDAI_ASET.md`.

| Tugas | Pilihan | Lisensi (menurut hasil pindai) |
|---|---|---|
| Suara jadi teks | Whisper large-v3-turbo (bahasa Indonesia didukung) | MIT |
| Suara jadi teks (alternatif) | sea-asr-id (khusus bahasa Indonesia, bisa jalan di CPU) | belum terverifikasi |
| Otak penyusun rencana | Qwen3 8B (kelas 7-8 miliar) | Apache 2.0 |
| Mata (wajah dan suasana) | Qwen3-VL 4B (alternatif SmolVLM2) | Apache 2.0 |
| Pisah orang dan latar | BiRefNet | MIT |
| Perakit video | FFmpeg ditambah mesin animasi teks | FFmpeg belum dipindai, perlu dicek |
| Pengganti b-roll | footage milik Pak Guru dan latar buatan kode | n/a |

Catatan penting:
- Model yang lebih baru (Gemma 4, Qwen 3.6 dan 3.8, ukuran 27 miliar ke atas) terlalu berat untuk RAM 16 GB. Ukuran 8 miliar tetap yang terkuat dan aman.
- BiRefNet bekerja per gambar, jadi tepi bisa berkedip di video. Perlu diuji. Model SAM dihindari karena lisensi Meta sendiri dengan akses terbatas.
- AI pembuat video baru (b-roll AI) tidak realistis di laptop ini, jadi tidak dipakai.

### Mesin render [BELUM DIPUTUSKAN]
Remotion bersifat *source-available* dan perusahaan perlu lisensi berbayar, jadi **dihindari**. Pilihan gratis: HyperFrames (Apache-2.0), Motion Canvas (MIT), Revideo (MIT). Perlu diputuskan mana yang dipakai.

### Cara memasang AI [BELUM DIPUTUSKAN]
Model AI (8-12 GB) dibawa langsung di installer, atau diunduh sekali saat pertama dipakai dari Hugging Face. **Saran Claude:** diunduh saat pertama dipakai.

---

## 6. Perkiraan waktu proses

Perkiraan kasar untuk laptop Pak Guru, video 60 detik, 1080p, 30 fps. Angka pasti baru diketahui setelah diuji.

| Tahap | Perkiraan |
|---|---|
| Baca video dan ambil audio | sekitar 10 detik |
| Suara jadi teks | 1-2 menit |
| Lihat wajah dan suasana | 1-2 menit |
| Susun rencana motion | 4-6 menit |
| Pisah orang dan latar | 3-5 menit |
| Render dan ekspor 1080p | 3-6 menit |
| **Total** | **sekitar 12-22 menit** |

- Ukuran aplikasi dengan model AI: sekitar 8-12 GB. Pastikan penyimpanan laptop cukup.
- Selama proses, kipas laptop bekerja keras dan aplikasi lain sebaiknya ditutup.
- Antrean beberapa video memungkinkan ditinggal semalaman.

---

## 7. Penilaian dibanding aplikasi referensi

Semua angka adalah perkiraan, karena referensi hanya dilihat dari satu tangkapan layar dan Cherry MotionPlus belum dibangun.

| Aspek | Referensi | Cherry MotionPlus |
|---|---|---|
| Kemudahan (3 langkah) | 9 | 9 |
| Mutu rencana motion | 8-9 | 7 |
| Gambar pendukung (b-roll) | 8 | 4 |
| Transkrip bahasa Indonesia | 8 | 9 |
| Pisah orang dan latar | 8 | 8 |
| Kecepatan proses | 8 | 5 |
| Kontrol pengguna | 6 | 9 |
| Biaya dan privasi | 5 | 10 |
| Bisa dipakai di HP | 9 | 3 |
| **Rata-rata** | **sekitar 7,7** | **sekitar 7,1** |

Kelemahan utama Cherry: b-roll dan kecepatan. Keunggulan: kontrol, privasi, dan gratis.

---

## 8. Pustaka suara, musik, dan latar

Pak Guru tidak punya waktu mengumpulkan aset, jadi Claude yang memindai sumber gratis (hasil lengkap di `HASIL_PINDAI_ASET.md`).

Strategi [USULAN yang sejalan dengan arah diskusi]:
- **Efek suara (whoosh, klik, pop, dan lainnya):** paket awal berlisensi CC0 yang dikumpulkan lewat skrip di laptop Pak Guru. File suara **belum diunduh ke repo ini**; repo hanya berisi katalog sumber dan lisensinya.
- **Efek suara buatan kode:** Claude dapat membuat suara sederhana yang original dan bebas hak cipta sebagai cadangan.
- **Latar bergerak:** dibuat lewat kode (partikel, gelombang, kertas tua), tanpa footage.
- **Musik dan footage:** tidak dibawa di dalam installer, karena menyertakan file lepasan bisa melanggar lisensi. Pak Guru mengunduh sendiri lewat "Folder Pustaka Saya".
- **Musik latar [BELUM DIPUTUSKAN]:** satu-satunya kebutuhan yang belum punya jalur pasti.

---

## 9. Aturan yang berlaku untuk aplikasi ini

- **Diskusi dulu.** Kode tidak diubah atau dibangun sebelum ada perintah eksplisit.
- **Footer tetap:** `Cherry MotionPlus ©2026 | totogutomo.com`
- **Bagian Tentang:** tulis "Guru SMA Negeri 3 Maliku" di bawah nama pembuat.
- **Mockup:** disimpan di folder `docs/mockup` repo ini, hanya didorong atas perintah atau konfirmasi Pak Guru.
- **Perubahan kecil:** hanya bagian yang disebut yang diubah, hasil akhir tetap utuh dan siap pakai.

---

## 10. Keputusan yang masih terbuka

1. Daftar gaya motion untuk versi 1 (usulan: 5 gaya).
2. Mesin render yang dipakai (bukan Remotion).
3. Cara memasang model AI (bawa di installer atau unduh saat pertama).
4. Sumber musik latar.
5. Beli aplikasi referensi (Rp99 ribu) atau bangun sendiri. **Saran Claude:** beli dulu sebagai pembanding, tetapi cek apakah sekali bayar atau langganan dan apakah ada batas jumlah video. Bangun sendiri sepadan bila tujuannya gratis tanpa batas, offline, privasi, gaya khas (Nuansa Kalimantan, Sejarah Klasik), atau menjadi karya dan bahan buku.

Langkah berikutnya: putuskan poin 2 sampai 4, lalu pindah ke sesi baru dengan prompt serah terima, dan mockup dibuat bila konsep sudah matang.

---

Cherry MotionPlus ©2026 | totogutomo.com
