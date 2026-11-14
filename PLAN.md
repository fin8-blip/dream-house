# PLAN.md — Dream House 3D (Survival Walkthrough HD)

Rencana kerja & log game **Dream House** — bangun rumah voxel, lalu **masuk dan jalan-jalan di dalamnya** dengan POV survival (jalan, lari, lompat, pasang/hancur blok). Semua dalam **1 file `index.html`** tanpa dependensi.

---

## 1. Ikhtisar

- **Judul**: Dream House 3D — Survival Walkthrough HD
- **Genre**: Voxel sandbox / survival-walkthrough
- **Format**: Single-File HTML, WebGL murni (shader ditulis manual), tanpa library
- **Kamera**: First-person (POV survival), mouse look / pointer lock
- **Dunia**: 24 × 12 × 24 blok
- **Tekstur**: Atlas prosedural **64 px** (HD), 22 tile, mipmap
- **Fisika**: Gravitasi, lompat, tabrakan AABB per-sumbu, step sub-frame
- **Interaksi**: Raycast DDA — hancurkan (klik kiri), pasang (klik kanan), ambil blok (klik tengah)
- **Kontrol**: WASD, Spasi, Shift, 1–9, E, F, Esc + joystick & tombol sentuh di HP
- **Audio**: Web Audio API sintetis
- **Penyimpanan**: LocalStorage (`dreamhouse_survival_world`, `dreamhouse_survival_user`)
- **Kebijakan Caching**: Zero-Cache
- **Deployment**: GitHub Pages — https://fin8-blip.github.io/dream-house/

---

## 2. Keputusan Desain

| Aspek | Keputusan |
|---|---|
| Judul | Dream House |
| Sudut pandang | First-person survival (bukan lagi isometrik) |
| Gerakan | Jalan, lari, **lompat**, jatuh dengan gravitasi |
| Blok | 19 jenis: struktur, alam, dan **furniture HD** |
| Furniture | Blok tinggi parsial (kasur 0.5, sofa 0.55, meja 0.6, dst.) agar terlihat seperti barang, bukan kubus penuh |
| Bangun | Pasang/hancur langsung dari POV pertama lewat crosshair |
| Mode terbang | Toggle `F` untuk membangun lebih mudah |
| Dunia awal | Rumah contoh lengkap dengan perabot, jalan setapak, dan tanaman |

---

## 3. Fase Pengembangan

### Phase 0: Brainstorming ✅
- [x] Ide awal game bersih-bersih ala House Flipper
- [x] Pivot ke mainan arsitektur mini berbasis petak isometrik
- [x] Judul **Dream House**
- [x] Pivot ke 3D walkthrough
- [x] **Pivot final: POV survival first-person + HD**

### Phase 1: Engine WebGL ✅
- [x] Canvas fullscreen + devicePixelRatio
- [x] Shader vertex/fragment manual (lighting per-face + fog)
- [x] Atlas tekstur prosedural 64 px (22 tile) + mipmap
- [x] Depth test, alpha discard untuk tanaman/lampu

### Phase 2: Dunia & Mesh ✅
- [x] Grid 24×12×24 (`Uint8Array`)
- [x] Mesh builder dengan face culling + dukungan blok tinggi parsial
- [x] Indeks 32-bit (`OES_element_index_uint`) bila tersedia
- [x] Rumah contoh: dinding bata, jendela kaca, pintu tinggi, atap melandai berundak, perabot

### Phase 3: Fisika Survival ✅
- [x] Gravitasi, kecepatan terminal, lompat 1.36 blok
- [x] Tabrakan AABB per-sumbu dengan sub-step (anti-tembus)
- [x] Deteksi `grounded` untuk lompat
- [x] Batas dunia + respawn saat jatuh
- [x] Mode terbang (F)

### Phase 4: Interaksi ✅
- [x] Raycast DDA (jarak 6 blok)
- [x] Outline blok target
- [x] Hancurkan / pasang / ambil blok
- [x] Cegah menaruh blok di dalam tubuh pemain
- [x] Undo (Ctrl+Z / tombol)
- [x] Simpan otomatis ke LocalStorage

### Phase 5: UI ✅
- [x] Hotbar 9 slot + angka 1–9 + scroll
- [x] Katalog blok (E) untuk mengganti isi slot
- [x] Crosshair, hint kontrol, toast
- [x] Pause overlay + pointer lock
- [x] Foto PNG

### Phase 6: Mobile ✅
- [x] Deteksi perangkat sentuh
- [x] Joystick kiri, geser layar untuk melihat
- [x] Tombol LOMPAT / PASANG / HANCUR
- [x] FOV adaptif untuk layar portrait

### Phase 7: Publikasi ✅
- [x] Repo publik `fin8-blip/dream-house`
- [x] GitHub Pages aktif (branch `main`, root)
- [x] Zero-cache

---

## 4. Matriks Tugas

| ID | Tugas | Status |
| :--- | :--- | :--- |
| T-01 | Engine WebGL + shader + atlas HD | `DONE` |
| T-02 | Mesh builder dengan tinggi blok parsial | `DONE` |
| T-03 | Fisika gravitasi, lompat, tabrakan | `DONE` |
| T-04 | Raycast & pasang/hancur blok | `DONE` |
| T-05 | Hotbar + katalog + undo | `DONE` |
| T-06 | Rumah contoh + perabot HD | `DONE` |
| T-07 | Kontrol sentuh HP | `DONE` |
| T-08 | Simpan lokal + foto | `DONE` |
| T-09 | Deploy GitHub Pages | `DONE` |
| T-10 | Siklus siang/malam | `TODO` |
| T-11 | Sistem hari/uang & misi klien | `TODO` |
| T-12 | Multi-lantai & tangga | `TODO` |

---

## 5. Changelog

| Versi | Tanggal | Ringkasan |
| :--- | :--- | :--- |
| **v3.0.0** | 2026-11-14 | Pivot ke POV survival first-person: gravitasi, jalan/lari/lompat, tabrakan AABB, raycast pasang & hancur blok, 19 blok termasuk furniture HD, tekstur 64 px, fog & lighting, hotbar + katalog, mode terbang, kontrol sentuh, rumah contoh lengkap |
| v2.0.0 | 2026-11-14 | Upgrade ke 3D WebGL (walkthrough + architect isometrik) |
| v1.0.0 | 2026-11-14 | Rilis isometrik 2.5D: 27 item, Mode Bebas & Tantangan, leaderboard |
