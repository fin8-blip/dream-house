# PLAN.md — Dream House: Mini Architect

Rencana kerja & log perkembangan game **Dream House** — mainan arsitektur mini berbasis petak isometrik dalam **1 file `index.html`**.

---

## 1. Ikhtisar Game

- **Judul**: **Dream House** — *Mini Architect*
- **Tagline**: "Susun rumah impianmu di atas papan petak."
- **Genre**: Bangun & dekorasi (sandbox builder) isometrik 2.5D
- **Format**: Single-File HTML (`index.html`), Vanilla JS + Canvas 2D, tanpa dependensi
- **Kamera**: Isometrik 2.5D (diorama/maket), zoom + pan
- **Mode**:
  1. **Mode Bebas** — papan kosong, semua item terbuka, tanpa batas & tanpa skor
  2. **Mode Tantangan** — brief klien + anggaran koin + mini-task bersih-bersih + bintang
- **Audio**: Web Audio API sintetis
- **Penyimpanan**: LocalStorage (`arcade_last_username`, `arcade_leaderboard`, `dreamhouse_save_v1`)
- **Kebijakan Caching**: Zero-Cache (`no-cache, no-store, must-revalidate`)
- **Deployment**: GitHub Pages (repo baru, branch `main`, path `/`)
- **Lokasi proyek**: folder `dream-house/` — game lama *Survival Block 3D* di root tetap utuh

---

## 2. Keputusan Desain (Hasil Brainstorming)

| Aspek | Keputusan |
|---|---|
| Judul | **Dream House** |
| Tampilan papan | **Isometrik 2.5D** — terasa seperti maket mainan di atas meja |
| Rasa permainan | **Santai**; timer tidak wajib |
| Fokus versi pertama | **Mode Bebas + Mode Tantangan sekaligus** |
| Mekanik bersih-bersih | **Dipertahankan** sebagai mini-task di awal Mode Tantangan |
| Papan | Grid **14 × 14** petak, tiap petak punya lapisan lahan + objek |
| Rotasi objek | Ditunda ke versi berikutnya |

---

## 3. Fase Pengembangan

### Phase 0: Brainstorming ✅
- [x] Ide awal: game bersih-bersih ala House Flipper
- [x] Pivot ke mainan arsitektur mini berbasis petak
- [x] Judul disepakati: **Dream House**
- [x] Tampilan isometrik 2.5D dipilih
- [x] Mode Bebas + Tantangan disepakati
- [x] Mini-task bersih-bersih dipertahankan untuk Mode Tantangan

### Phase 1: Kerangka Single-File ✅
- [x] `index.html` dengan meta tag Zero-Cache
- [x] Canvas fullscreen + `devicePixelRatio`
- [x] Struktur 8 blok kode (config, audio, input, state, geometri, storage, render, loop)

### Phase 2: Engine Isometrik ✅
- [x] Proyeksi `screenX = (x-y)·TW/2`, `screenY = (x+y)·TH/2`
- [x] Depth sorting berdasarkan `x + y`
- [x] Alas/pedestal diorama + bayangan objek
- [x] Kamera zoom (wheel/pinch) + pan (klik kanan / dua jari)
- [x] Picking petak (layar → grid) untuk hover & penempatan

### Phase 3: Bangun & Dekorasi ✅
- [x] 30 item: lahan, struktur, furniture, halaman
- [x] Penempatan klik & drag (gambar baris dinding sekaligus)
- [x] Penghapus objek & penghapus lahan
- [x] Undo / Redo (maks 80 langkah)
- [x] Pratinjau hantu (ghost) saat hover
- [x] Partikel kilau saat menaruh/ membersihkan

### Phase 4: Mode Bebas ✅
- [x] Papan kosong, semua item terbuka, tanpa biaya
- [x] Simpan otomatis ke `dreamhouse_save_v1`
- [x] Papan Baru (reset)
- [x] Foto diorama (unduh PNG dengan cap nama)

### Phase 5: Mode Tantangan ✅
- [x] 3 tantangan: Rumah Mungil, Villa Pantai, Rumah Keluarga
- [x] Sistem anggaran koin (biaya per item, refund saat dihapus)
- [x] Mini-task bersih-bersih (noda petak, spons, 2 kali gosok)
- [x] Checklist permintaan klien live
- [x] Penilaian bintang 1–3 + skor
- [x] Papan peringkat Top 10 per tantangan

### Phase 6: Identitas & UI ✅
- [x] Modal username (validasi 1–15 karakter, sanitasi XSS)
- [x] Menu utama: Mode Bebas, daftar tantangan, papan peringkat, ganti nama
- [x] HUD: mode, koin, undo/redo, foto, simpan, selesai
- [x] Panel checklist tantangan
- [x] Palet kategori + item dengan ikon & harga
- [x] Responsif HP/tablet (palet scroll, pinch zoom)

### Phase 7: Publikasi
- [ ] Inisialisasi repo baru `dream-house`
- [ ] Push ke GitHub publik
- [ ] Aktifkan GitHub Pages
- [ ] Verifikasi live + zero-cache

---

## 4. Matriks Tugas

| ID | Tugas | Fase | Status |
| :--- | :--- | :--- | :--- |
| T-01 | Engine isometrik + picking petak | Phase 2 | `DONE` |
| T-02 | Katalog 30 item + render prosedural | Phase 3 | `DONE` |
| T-03 | Penempatan, drag-paint, undo/redo | Phase 3 | `DONE` |
| T-04 | Mode Bebas + simpan lokal | Phase 4 | `DONE` |
| T-05 | Mode Tantangan + anggaran + bintang | Phase 5 | `DONE` |
| T-06 | Mini-task bersih-bersih | Phase 5 | `DONE` |
| T-07 | Username + leaderboard Top 10 | Phase 6 | `DONE` |
| T-08 | Foto diorama | Phase 4 | `DONE` |
| T-09 | Kontrol sentuh & UI responsif | Phase 6 | `DONE` |
| T-10 | Deploy GitHub Pages | Phase 7 | `TODO` |
| T-11 | Rotasi objek 4 arah | v1.1 | `TODO` |
| T-12 | Siang/malam + lampu menyala | v1.1 | `TODO` |
| T-13 | Galeri rumah & katalog terbuka | v1.2 | `TODO` |
| T-14 | Tema rumah (pantai, Jepang, Skandinavia) | v2 | `TODO` |

---

## 5. Changelog

| Versi | Tanggal | Ringkasan |
| :--- | :--- | :--- |
| **v1.0.0** | 2026-11-14 | Rilis pertama: engine isometrik 14×14, 30 item, Mode Bebas & 3 Tantangan, mini-task bersih-bersih, anggaran koin, bintang, username, leaderboard, simpan lokal, foto diorama, kontrol sentuh |
