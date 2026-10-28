# Cherry MotionPlus: Hasil Pindai Aset dan Sumber Gratis

Tanggal pindai: 28 Oktober 2026
Pembuat: Toto Gutomo, Guru SMA Negeri 3 Maliku

## Cara membaca dokumen ini

- Ini **katalog sumber dan lisensi**, bukan kumpulan file. **Tidak ada file suara, musik, footage, atau model AI yang diunduh ke repo ini.** Alasannya: akses unduhan dari lingkungan kerja Claude terbatas, dan sebagian sumber (musik, footage) tidak boleh dibagikan ulang sebagai file lepasan.
- Semua temuan berasal dari halaman web hasil pencarian (blog, katalog, halaman model). **Lisensi harus dicek ulang di halaman resmi tiap model atau paket sebelum dipakai.**
- Status tiap sumber:
  - **PAKAI:** lisensi longgar menurut hasil pindai.
  - **HATI-HATI:** ada syarat atau perlu dicek.
  - **HINDARI:** tidak cocok untuk aplikasi ini.

---

## 1. Model AI (Hugging Face dan lainnya)

### Suara jadi teks

| Sumber | Status | Catatan |
|---|---|---|
| Whisper large-v3-turbo (https://huggingface.co/openai/whisper-large-v3-turbo) | PAKAI | 809 juta parameter, bahasa Indonesia didukung. Halaman katalog mencatat lisensi MIT; beberapa salinan komunitas mencatat Apache-2.0. Cek halaman resmi. Rujukan: https://superlinked.com/models/openai-whisper-large-v3-turbo |
| sea-asr-id (https://huggingface.co/PixelML/sea-asr-id) | HATI-HATI | Khusus bahasa Indonesia. Setara Whisper turbo pada ucapan terbaca, lebih baik pada percakapan, bisa jalan di CPU. **Lisensi belum terverifikasi.** |

### Otak penyusun rencana motion (LLM)

| Sumber | Status | Catatan |
|---|---|---|
| Qwen3 (4B dan 8B) | PAKAI | Apache 2.0, tanpa batas pengguna atau batasan komersial. Untuk laptop 16 GB, 4B dan 8B adalah yang praktis. Rujukan: https://huggingface.co/blog/daya-shankar/open-source-llm-models-to-run-locally |
| Gemma 3 4B, Phi-4-mini | HATI-HATI | Muat di 16 GB, tetapi lisensi belum dicek di pindai ini. Sumber yang sama. |
| Gemma 4, Qwen3.6, Qwen3.8 (27B ke atas) | HINDARI | Apache-2.0 tetapi terlalu besar untuk RAM 16 GB. Rujukan: https://www.morphllm.com/best-open-source-llm dan https://huggingface.co/blog/daya-shankar/open-source-llms |

Menjalankan model lewat alat lokal seperti llama.cpp, Ollama, atau LM Studio (disebut di sumber di atas).

### Mata (wajah dan suasana)

Rujukan perbandingan: https://aiidelist.com/blog/on-device-vlm-comparison

| Sumber | Status | Catatan |
|---|---|---|
| Qwen3-VL (2B, 4B, 8B) (https://huggingface.co/collections/Qwen/qwen3-vl) | PAKAI | Apache 2.0, kuat untuk teks dalam gambar dan video. Pilihan utama ukuran 4B. |
| SmolVLM2 (256M, 500M, 2.2B) (https://huggingface.co/blog/smolvlm2) | PAKAI | Apache 2.0, sangat ringan, memahami video. Cadangan untuk mode Cepat. |
| Moondream 2 | PAKAI | Apache 2.0. Moondream 3 punya syarat lisensi berbeda, cek dulu. |
| LFM2.5-VL | HATI-HATI | Memakai "LFM Open License", bukan Apache. |

### Pemisah orang dan latar

| Sumber | Status | Catatan |
|---|---|---|
| BiRefNet | PAKAI | Lisensi MIT. Bekerja per gambar, tepi bisa berkedip di video, perlu diuji. Rujukan: https://ice-ice-bear.github.io/posts/2026-04-15-birefnet/ |
| nobg (https://pypi.org/project/nobg/) | HATI-HATI | Pustaka Python berlisensi Apache-2.0 untuk image dan video matting. Lisensi tiap model di dalamnya perlu dicek. |
| BEN v2, Bria | HATI-HATI | Mendukung video dengan alpha. Lisensi belum dipindai. Rujukan: https://invideo.io/blog/ai-background-removal-models/ |
| SAM (Meta) | HINDARI | Lisensi Meta sendiri dengan checkpoint terbatas, bukan lisensi terbuka biasa. |

---

## 2. Efek suara

| Sumber | Status | Catatan |
|---|---|---|
| Repo GitHub opus-sound-layer (https://github.com/Bodila51/opus-sound-layer) | PAKAI | Skrip `sfx.py kit` mengunduh sekitar 1.139 suara CC0 dalam 19 jenis (hit, boom, riser, transition, whoosh, swish, glitch, ui, click, key, tick, tap, pop, thump, paper, chime, shimmer, zap), dari paket Kenney dan rekaman Freesound. Suara tidak disimpan di repo; daftar kredit ada di `audio/kit/CREDITS.md`. **Skrip dijalankan di laptop Pak Guru.** Lisensi skripnya sendiri perlu dicek. |
| Freesound dengan filter CC0 | PAKAI | Filter lisensi CC0 wajib; lisensi per suara berbeda. Rujukan: https://app.cinevva.com/guides/free-sound-effects-music |
| 99Sounds Cinematic Transitions (https://99sounds.org/?p=2387) | HATI-HATI | 50 transisi, royalti-bebas. Cek apakah boleh dibawa di dalam aplikasi. |
| Sonniss GDC bundle | HATI-HATI | Bebas royalti komersial tanpa atribusi, arsip sangat besar (200 GB lebih). Dipilih per suara saja. Rujukan: cinevva (di atas). |
| RouteNote Licensing, koleksi transisi (https://licensing.routenote.com/blog/collection-highlight-transition-sound-effects/) | HATI-HATI | Ada yang CC0 gratis, ada yang berbayar. |
| Mixkit sound effects | HATI-HATI | Lisensi Mixkit membolehkan komersial tanpa atribusi, tetapi syarat membagikan ulang perlu dibaca. |
| Dataset Freesound LAION 640k di Hugging Face (https://huggingface.co/datasets/0x3/freesound-laion-640k) | HATI-HATI | Lisensi berbeda per suara (ada kolom atribusi). Hanya ambil yang CC0. |
| Paket gratis berlisensi khusus (contoh SwiftFX Lite, https://payhip.com/b/o6Ayh) | HINDARI untuk dibundel | Boleh dipakai di proyek sendiri, tetapi dilarang dibagikan ulang sebagai file lepasan. |
| Dataset Epidemic Sound effects di Hugging Face | HINDARI | Konten perpustakaan suara komersial; kejelasan hak pakai tidak ada. |
| Pro Sound Effects AI/ML sample (https://huggingface.co/datasets/ProSoundEffects/pse-audio-sfx-dataset) | HINDARI | Sampel evaluasi non-komersial dan berakses terbatas. |

Cadangan: Claude dapat membuat efek suara sederhana lewat kode (whoosh, klik, pop, ding). Hasilnya original dan bebas hak cipta, tetapi terdengar lebih sederhana.

---

## 3. Musik latar

| Sumber | Status | Catatan |
|---|---|---|
| FreePD | PAKAI | Seluruhnya CC0. Rujukan: https://maketecheasier.com/websites-download-royalty-free-music/ |
| Pixabay Music | HATI-HATI | Komersial tanpa atribusi, tetapi file lepasan tidak boleh dijual, dan bisa memicu klaim otomatis di YouTube. Rujukan: https://app.cinevva.com/guides/free-sound-effects-music dan https://www.itechguides.com/?p=349194 |
| Free Music Archive | HATI-HATI | Lisensi per lagu; filter CC0. Rujukan: https://lesfm.net/blog/free-background-music |
| Incompetech | HATI-HATI | Perlu atribusi atau lisensi berbayar. Rujukan: itechguides (di atas) |
| Bensound | HINDARI | Wajib kredit dan tidak boleh dimodifikasi. Rujukan: maketecheasier (di atas) |

**Keputusan sumber musik latar masih terbuka.** Usulan: musik tidak dibawa di installer; Pak Guru mengunduh sendiri lewat "Folder Pustaka Saya".

---

## 4. Latar bergerak dan footage

| Sumber | Status | Catatan |
|---|---|---|
| Pexels Videos | HATI-HATI | Gratis komersial tanpa atribusi. Jangan dibagikan ulang sebagai file lepasan. Rujukan: https://videobgremover.com/blog/animated-backgrounds-free |
| Pixabay Videos | HATI-HATI | Sama seperti di atas. |
| Mixkit (video) | HATI-HATI | Komersial tanpa atribusi. |
| Coverr | HINDARI untuk dibundel | Boleh dipakai, tetapi tidak boleh dibagikan ulang. |

Usulan: latar bergerak dibuat lewat kode (partikel, gelombang, kertas tua). Footage nyata dipakai lewat "Folder Pustaka Saya", tidak dibawa di installer.

---

## 5. Mesin render video

Rujukan: https://capitalandcompute.net/blog/best-open-source-ai-video-tools/ dan https://www.remotion.dev/docs/compare/motion-canvas

| Sumber | Status | Catatan |
|---|---|---|
| HyperFrames | PAKAI | Apache-2.0. Kemampuannya belum dipindai mendalam. |
| Motion Canvas | PAKAI | MIT, sumber terbuka sepenuhnya. Hanya merender konten berbasis kanvas. |
| Revideo | PAKAI | MIT. |
| Remotion | HINDARI | *Source-available*, bukan sumber terbuka; perusahaan perlu lisensi berbayar. Komponen MIT untuk Remotion (https://github.com/Curvable/motion) tetap bergantung pada lisensi Remotion. |
| FFmpeg | BELUM DIPINDAI | Perlu dicek lisensi build yang dipakai. |

---

## 6. Catatan penutup

- Pindai ini dilakukan dengan pencarian web, bukan pemeriksaan langsung tiap repo atau model. Anggap semua lisensi sebagai **dugaan awal yang harus diverifikasi**.
- Bila aplikasi ini kelak dibagikan atau dijual ke orang lain, jalur paling aman adalah: aplikasi hanya membawa aset CC0 yang jelas, dan musik serta footage disediakan pengguna sendiri.

Cherry MotionPlus ©2026 | totogutomo.com
