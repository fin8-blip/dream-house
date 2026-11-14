# PLAN.md — Dream House Flipper 3D (Realistic Interior)

Game renovasi rumah ala **House Flipper**: masuk ke rumah, bersihkan kotoran, cat dinding, dan dekorasi ruangan dengan furnitur. Bukan voxel — memakai interior low-poly dengan dinding tipis, pintu, jendela, plafon, dan perabot halus.

---

## 1. Ikhtisar

- **Judul**: Dream House — House Flipper 3D
- **Format**: Single-File HTML, WebGL murni (tanpa library/aset eksternal)
- **Kamera**: First-person (jalan, lari, lompat, tabrakan)
- **Rumah**: 5 ruang — Ruang Tamu, Kamar Tidur, Dapur, Kamar Mandi, Lorong
- **Geometri**: bukan blok — dinding tipis 14 cm, bukaan pintu/jendela, plafon, plint
- **Perabot**: 12 model prosedural (sofa, kasur, lemari, TV, meja, rak, tanaman, dll.)
- **Kotoran**: 634 sel permukaan dengan tekstur noda, dibersihkan per area
- **Cat**: 4 warna (Krem, Hijau, Biru, Terracotta)
- **Ekonomi**: anggaran renovasi 🪙 12.000
- **Audio**: Web Audio API sintetis
- **Deployment**: https://fin8-blip.github.io/dream-house/

---

## 2. Alur Permainan

1. **Masuk rumah** — interior kotor, lantai kayu, dinding penuh noda.
2. **Bersihkan** 🧽 — gosok dinding/lantai/jendela; noda memudar per area.
3. **Cat dinding** 🎨 — pilih warna, arahkan ke dinding, klik.
4. **Dekorasi** 🛋️ — pilih furnitur dari katalog, putar dengan R, taruh di lantai.
5. **Selesaikan** ⭐ — nilai kebersihan, jumlah dinding dicat, furnitur, sisa anggaran.

---

## 3. Penilaian

| Komponen | Nilai |
|---|---|
| Kebersihan | 1.000 |
| Dinding dicat | 120 / segmen |
| Furnitur | 150 / item |
| Sisa anggaran | 0,2 / koin |

**Bintang**
- ★ — kebersihan ≥ 60%
- ★★ — kebersihan ≥ 85% + ≥ 4 furnitur
- ★★★ — kebersihan ≥ 97% + ≥ 6 furnitur + ≥ 4 dinding dicat

---

## 4. Furnitur & Harga

| Item | Harga |
|---|---|
| Sofa | 🪙 1.200 |
| Kursi Malas | 🪙 650 |
| Meja Kopi | 🪙 450 |
| TV | 🪙 900 |
| Kasur | 🪙 1.600 |
| Lemari | 🪙 1.400 |
| Meja Kerja | 🪙 700 |
| Kursi | 🪙 300 |
| Karpet | 🪙 400 |
| Lampu Lantai | 🪙 450 |
| Tanaman | 🪙 350 |
| Rak Buku | 🪙 800 |

---

## 5. Kontrol

- **WASD** jalan · **Shift** lari · **Spasi** lompat
- **Klik Kiri** pakai alat · **R** putar furnitur
- **1–9** ganti alat · **E** katalog
- **F** terbang · **Esc** jeda
- **HP**: joystick + tombol LOMPAT / PAKAI / PUTAR

---

## 6. Status

| ID | Tugas | Status |
| :--- | :--- | :--- |
| T-01 | Engine polygon (bukan voxel) + shader | `DONE` |
| T-02 | Rumah 5 ruang: dinding, pintu, jendela, plafon, plint | `DONE` |
| T-03 | 12 model furnitur prosedural | `DONE` |
| T-04 | Sistem kotoran per sel + spons | `DONE` |
| T-05 | Cat 4 warna per segmen dinding | `DONE` |
| T-06 | Penempatan furnitur + rotasi + tabrakan | `DONE` |
| T-07 | Panel pekerjaan & bintang | `DONE` |
| T-08 | Fisika first-person & collider | `DONE` |
| T-09 | UI responsif + kontrol sentuh | `DONE` |
| T-10 | Deploy GitHub Pages | `DONE` |
| T-11 | Beberapa rumah/klien berbeda | `TODO` |
| T-12 | Toko & upgrade alat | `TODO` |
| T-13 | Pencahayaan siang/malam | `TODO` |

---

## 7. Changelog

| Versi | Tanggal | Ringkasan |
| :--- | :--- | :--- |
| **v5.0.0** | 2026-11-14 | **Interior realistis**: ganti voxel dengan geometri polygon (dinding tipis, pintu, jendela, plafon, plint), 12 furnitur prosedural halus, sistem kotoran 634 sel dengan tekstur noda, cat 4 warna, panel pekerjaan & bintang, collider lantai/dinding/furnitur |
| v4.0.0 | 2026-11-14 | House Flipper voxel: grime per blok, spons, tambal retak, cat |
| v3.0.0 | 2026-11-14 | Survival first-person voxel |
| v1.0.0 | 2026-11-14 | Isometrik 2.5D |
