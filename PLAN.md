# PLAN.md — Dream House Flipper 3D

Game renovasi rumah **House Flipper-style** dalam **1 file `index.html`**: masuk ke rumah kotor, bersihkan, tambal dinding retak, cat ulang, isi furnitur, lalu selesaikan pekerjaan dan raih bintang.

---

## 1. Ikhtisar

- **Judul**: Dream House — House Flipper 3D
- **Genre**: Renovation sim / first-person sandbox
- **Format**: Single-File HTML, WebGL murni (tanpa library)
- **Kamera**: First-person survival (jalan, lari, lompat, gravitasi, tabrakan)
- **Dunia**: 24 × 12 × 24 blok
- **Tekstur**: Atlas prosedural **64 px**, 26 tile, mipmap
- **Sistem kotor**: layer `grime` per blok yang memengaruhi warna lewat shader
- **Alat**: Spons (gosok), Perbaiki (tambal retak), Cat (3 warna), Furnitur
- **Ekonomi**: anggaran renovasi 🪙 9.000
- **Audio**: Web Audio API sintetis
- **Penyimpanan**: LocalStorage (`dhf_world_v1`, `dhf_user`)
- **Deployment**: https://fin8-blip.github.io/dream-house/

---

## 2. Alur Permainan (House Flipper)

1. **Terima pekerjaan** — rumah tua Pak Budi, kotor dan retak.
2. **Bersihkan** — gosok dinding & lantai dengan spons (radius 1,5 blok per gosokan).
3. **Perbaiki** — tambal 8 titik dinding retak.
4. **Cat** — pilih salah satu dari 3 warna, cat dinding.
5. **Dekorasi** — beli & tempatkan furnitur sesuai anggaran.
6. **Selesaikan** — dapat bintang 1–3 dan skor akhir.

---

## 3. Sistem Penilaian

| Komponen | Bobot |
|---|---|
| Kebersihan (grime tersisa) | 1.000 |
| Retak ditambal | 120 / titik |
| Dinding dicat | 70 / blok |
| Furnitur terpasang | 160 / item |
| Sisa anggaran | 0,25 / koin |

**Bintang:**
- ★ — kebersihan ≥ 60%
- ★★ — kebersihan ≥ 85% **dan** semua retak ditambal
- ★★★ — kebersihan ≥ 97% + semua retak + ≥10 dinding dicat + ≥5 furnitur

---

## 4. Alat & Harga

| Alat | Fungsi |
|---|---|
| 🧽 Spons | Menggosok kotoran (radius 1,5 blok) |
| 🔨 Perbaiki | Mengubah dinding retak → dinding normal |
| 🎨 Cat Krim / Hijau / Biru | Mewarnai dinding |
| 🛏️ Kasur | 🪙 600 |
| 🛋️ Sofa | 🪙 500 |
| 🍽️ Meja | 🪙 300 |
| 🪑 Kursi | 🪙 150 |
| 📚 Rak Buku | 🪙 350 |
| 📺 TV | 🪙 450 |
| 🪴 Tanaman | 🪙 120 |
| 💡 Lampu | 🪙 200 |
| 🟥 Karpet | 🪙 150 |
| 🍳 Dapur | 🪙 700 |

---

## 5. Kontrol

- **WASD** jalan · **Shift** lari · **Spasi** lompat
- **Klik Kiri** pakai alat · **Klik Kanan** bongkar blok
- **1–9** ganti alat · **Scroll** ganti slot
- **E** katalog · **F** terbang · **Esc** jeda · **Ctrl+Z** undo
- **HP**: joystick kiri, geser layar untuk melihat, tombol LOMPAT / PAKAI / BONGKAR

---

## 6. Status

| ID | Tugas | Status |
| :--- | :--- | :--- |
| T-01 | Engine WebGL + atlas HD 64 px | `DONE` |
| T-02 | Sistem grime per blok (shader tint) | `DONE` |
| T-03 | Fisika survival: jalan, lompat, tabrakan | `DONE` |
| T-04 | Alat spons, perbaikan, cat 3 warna | `DONE` |
| T-05 | Penempatan furnitur + anggaran | `DONE` |
| T-06 | Panel pekerjaan & progres live | `DONE` |
| T-07 | Penilaian bintang & skor | `DONE` |
| T-08 | Kontrol sentuh HP | `DONE` |
| T-09 | Simpan lokal + undo + foto | `DONE` |
| T-10 | Deploy GitHub Pages | `DONE` |
| T-11 | Beberapa rumah / level klien | `TODO` |
| T-12 | Toko upgrade alat | `TODO` |
| T-13 | Siklus siang/malam | `TODO` |

---

## 7. Changelog

| Versi | Tanggal | Ringkasan |
| :--- | :--- | :--- |
| **v4.0.0** | 2026-11-14 | **House Flipper mode**: layer kotoran (grime) dengan tint shader, spons radius, tambal retak, cat 3 warna, furnitur berbayar, panel pekerjaan, penilaian bintang, rumah contoh kotor |
| v3.0.0 | 2026-11-14 | POV survival first-person: gravitasi, lompat, tabrakan, pasang/hancur blok, 19 blok, tekstur 64 px |
| v2.0.0 | 2026-11-14 | 3D WebGL walkthrough + isometrik |
| v1.0.0 | 2026-11-14 | Isometrik 2.5D, 27 item, leaderboard |
