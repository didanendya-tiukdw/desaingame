# Referensi Palet Warna

Dokumen ini mencatat token warna untuk landing page dan materi interaktif Game AI. Tema halaman mengikuti preferensi terang/gelap sistem, dengan pemilih tema manual.

## Tema gelap

| Token | Nilai | Penggunaan |
|---|---|---|
| `--bg` | `#0d1319` | Latar halaman |
| `--surface` / `--panel` | `#141d27` | Kartu dan panel |
| `--surface-raised` / `--panel2` | `#18232f` | Elemen sekunder yang ditinggikan |
| `--surface-soft` | `#1d2a37` | Latar lembut, badge, dan hover |
| `--text` | `#e8edf5` | Teks utama |
| `--muted` | `#8da0b5` | Teks sekunder |
| `--line` | `#263545` | Border dan pemisah |
| `--accent` | `#f4773b` | Aksen utama dan tombol |
| `--accent-ink` | `#111821` | Teks di atas aksen |
| `--orange` | `#ff8043` | Aksen oranye pendamping |
| `--hero-grid` | `rgba(129, 158, 190, .07)` | Grid dekoratif pada hero |

## Tema terang

| Token | Nilai | Penggunaan |
|---|---|---|
| `--bg` | `#f3f5f9` | Latar halaman |
| `--surface` / `--panel` | `#ffffff` | Kartu dan panel |
| `--surface-raised` / `--panel2` | `#f8fafd` | Elemen sekunder yang ditinggikan |
| `--surface-soft` | `#edf1f6` | Latar lembut, badge, dan hover |
| `--text` | `#17263d` | Teks utama dan aksen utama |
| `--muted` | `#607087` | Teks sekunder |
| `--line` | `#d8e0eb` | Border dan pemisah |
| `--accent` | `#17263d` | Aksen utama dan tombol |
| `--accent-ink` | `#ffffff` | Teks di atas aksen |
| `--orange` | `#e85a18` | Aksen oranye |
| `--hero-grid` | `rgba(39, 67, 102, .07)` | Grid dekoratif pada hero |

## Warna status materi Game AI

Warna status menjaga keterbacaan diagram dan indikator khusus dalam modul.

| Status | Tema gelap | Tema terang |
|---|---|---|
| Patrol / informasi | `#44d5dc` | `#087e91` |
| Chase | `#ae98ff` | `#6559b8` |
| Attack / peringatan | `#ff7b8c` | `#b52f54` |
| Berhasil | `#4ee2ac` | `#087d5b` |
| Perhatian | `#ffd083` | `#9b5f09` |
| Error | `#ff7d95` | `#b52f54` |

## Lokasi penerapan

- Landing page: [`index.html`](./index.html), pada token `:root` dan `html[data-theme="light"]`.
- Materi Game AI: [`10_Game_AI_Interactive.css`](./10_Game_AI_Interactive.css), menggunakan `--panel` dan `--panel2` sebagai padanan `--surface` dan `--surface-raised`.
