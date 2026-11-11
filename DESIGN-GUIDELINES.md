# Design Guidelines — Desain Game

Panduan ini menjaga tampilan landing page dan materi interaktif tetap konsisten. Gunakan [PALETTE-WARNA.md](./PALETTE-WARNA.md) sebagai referensi nilai warna.

## Prinsip visual

- **Jelas dan terarah:** hierarki judul, materi, dan aksi harus mudah dipindai.
- **Ruang untuk konten:** gunakan whitespace dan kartu dengan batas halus, bukan dekorasi berlebihan.
- **Interaktif dengan tujuan:** hover, filter, navigasi, dan simulasi memberi umpan balik yang jelas.
- **Konsisten lintas tema:** struktur dan hierarki sama dalam tema terang maupun gelap; ubah token warna, bukan tata letak.
- **Responsif:** konten harus tetap terbaca dan dapat digunakan dengan mouse, keyboard, maupun layar sentuh.

## Tipografi

### Font

- **Teks antarmuka dan isi:** `Inter`, dengan fallback sistem: `ui-sans-serif`, `system-ui`, `-apple-system`, `BlinkMacSystemFont`, `"Segoe UI"`, `sans-serif`.
- **Kode dan label teknis:** `ui-monospace`, `SFMono-Regular`, `Consolas`, monospace.
- Gunakan font sistem; jangan menambahkan font eksternal tanpa kebutuhan dan persetujuan.

### Skala ukuran

Ukuran dalam tabel adalah target CSS dalam piksel. `clamp()` menyesuaikan ukuran secara fluid.

| Peran | Ukuran | Bobot | Line-height / catatan |
|---|---:|---:|---|
| Judul hero landing | `clamp(42px, 6vw, 72px)`; mobile `clamp(44px, 12vw, 61px)` | 720 | `0.99`, tracking `-0.075em` |
| Judul bagian landing | `clamp(28px, 4vw, 40px)` | 690 | `1.1`, tracking `-0.055em` |
| Judul CTA penutup | 24px; mobile 21px | 690 | Mengikuti heading |
| Judul kartu pertemuan | 16px; mobile 14px | 670 | `1.35` |
| Isi utama materi | 15px | 400 | `1.55` |
| Deskripsi hero | 15px; mobile 13px | 400 | `1.8` |
| Intro dan navigasi | 12–13px | 400–650 | Umumnya `1.5–1.75` |
| Ringkasan kartu | 11px; mobile 10px | 400 | `1.7` |
| Metadata, kicker, dan badge | 9–11px | 650–850 | Huruf kapital dan letter-spacing |
| Judul bab pada modul | `clamp(29px, 3.4vw, 45px)` | 700 | `1.24` |
| Subjudul bab modul | `clamp(22px, 2.4vw, 30px)` | 700 | `1.24` |
| Judul kartu isi modul | 15–17px | 650–750 | `1.24` |
| Kode pada modul | 12–13px | 400 | Monospace, line-height sekitar `1.7` |

Gunakan bobot tebal untuk membedakan hierarki. Hindari memakai teks kecil di bawah 10px untuk informasi penting.

## Grid dan ukuran layout

- **Landing page:** konten berpusat dengan lebar responsif; hero, informasi mata kuliah, bagian materi, dan footer sejajar pada container yang sama.
- **Materi interaktif:** gunakan sidebar dan area utama; lebar shell maksimum `1840px`. Lebar sidebar desktop `252px`, menyusut menjadi `72px` pada layar lebih sempit.
- **Area baca modul:** padding utama desktop menggunakan `clamp(18px, 2.4vw, 38px)`.
- **Grid kartu materi:** 4 kolom pada desktop lebar, 3 kolom pada tablet, 2 kolom pada ponsel, dan 1 kolom pada layar sangat sempit.
- **Grid capaian:** 3 kolom pada desktop dan 1 kolom pada ponsel.
- **Grid konseptual modul:** 3 kolom desktop; susun ulang menjadi 2 kolom, lalu 1 kolom di layar kecil.
- Hindari lebar tetap untuk container utama dan anak grid. Gunakan `minmax(0, 1fr)` agar teks panjang tidak mendorong layout keluar viewport.

### Breakpoint yang digunakan

| Lebar viewport | Perilaku |
|---:|---|
| `≤ 1190px` | Modul merapatkan sidebar; container landing memakai gutter tablet |
| `≤ 950px` | Workspace modul menjadi satu kolom |
| `≤ 900px` | Hero dan grid kartu landing mulai disederhanakan |
| `≤ 680px` | Navigasi landing ringkas, hero bertumpuk, konten menggunakan gutter mobile |
| `≤ 650px` | Navigasi modul menjadi horizontal; konten modul satu kolom |
| `≤ 470px` | Ilustrasi modul dan kontrol ditumpuk agar nyaman disentuh |
| `≤ 380px` | Kartu pertemuan landing menjadi satu kolom |

## Spacing dan bentuk

Gunakan skala dasar berbasis kelipatan 4px; angka berikut adalah nilai yang sering dipakai:

| Jarak | Kegunaan |
|---:|---|
| 4–8px | Jarak ikon, badge, dan elemen rapat |
| 12–14px | Jarak antar kartu atau isi kontrol |
| 16–20px | Padding kartu dan jarak konten |
| 24–28px | Padding panel dan jarak antar kelompok |
| 34–48px | Padding hero desktop |
| 68–90px | Jarak vertikal antar bagian; kurangi pada ponsel |

- Kartu, panel, kontrol, dan tombol memakai sudut membulat. Gunakan radius sekitar 5–9px untuk badge/kontrol kecil, 12–16px untuk kartu, dan hingga 24px untuk hero.
- Gunakan border 1px dengan token `--line`.
- Gunakan bayangan secara halus untuk elevasi; jangan menjadikan bayangan sebagai pengganti kontras atau border.

## Komponen dan interaksi

- **Tombol utama:** satu aksi dominan per kelompok, warna mengacu ke token aksen, tinggi sekitar 46px, label singkat dan jelas.
- **Tombol sekunder:** latar permukaan, border halus, dan kontras teks yang memadai.
- **Kartu pertemuan:** tampilkan nomor, judul, ringkasan, tag, dan tautan/detail. Gunakan hover halus tanpa mengubah ukuran layout.
- **Navigasi dan filter:** status aktif harus terlihat selain melalui warna, misalnya dengan latar atau border; sediakan label aksesibel.
- **Detail yang dapat dibuka:** tampilkan affordance yang jelas, status terbuka/tertutup, serta konten yang terstruktur.
- **Transisi:** gunakan transisi singkat dan hormati `prefers-reduced-motion`.
- **Fokus keyboard:** jangan menghapus outline tanpa pengganti; gunakan indikator fokus kontras dan terlihat.

## Tema warna

- Gunakan token warna yang didefinisikan di [index.html](./index.html) dan [10_Game_AI_Interactive.css](./10_Game_AI_Interactive.css), bukan nilai warna baru yang tersebar.
- Tema terang menggunakan latar biru-abu muda, permukaan putih, teks navy, dan aksen oranye.
- Tema gelap menggunakan latar navy gelap, permukaan biru gelap, teks terang, dan aksen oranye.
- Gunakan `--muted` hanya untuk konten sekunder; teks penting harus memakai `--text`.
- Status simulasi (Patrol, Chase, Attack, berhasil, perhatian, error) dapat memakai warna status khusus yang tercatat di [PALETTE-WARNA.md](./PALETTE-WARNA.md).
- Selalu periksa kontras teks dan kontrol pada kedua tema.
- Tema awal mengikuti `prefers-color-scheme` sistem. Pemilih tema manual tetap tersedia.

## Aksesibilitas dan implementasi

- Gunakan elemen HTML semantik, judul berurutan, label untuk input, serta nama aksesibel untuk tombol ikon.
- Jangan menyampaikan status hanya dengan warna; tambahkan teks, ikon, atau label.
- Pastikan tombol dan kontrol dapat digunakan dengan keyboard dan target sentuh cukup nyaman.
- Landing page tetap berupa **single-file HTML** sesuai kebutuhan proyek. Untuk materi yang CSS-nya dipisah, simpan aturan pada stylesheet eksternal; hindari inline style.
- Uji tampilan di lebar desktop, tablet, dan ponsel, serta pada tema terang dan gelap sebelum menyelesaikan perubahan.
