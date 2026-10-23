# Functional Requirements Specification (FR-Spec)
**Project:** TaniPresisi AI - Smart Plantation & Sustainability Web App  
**Slug:** `tanipresisi-ai`  
**Pipeline Standard:** Antigravity Agentic Deterministic Pipeline (README.md & AGENTS.md)  
**Total FRs:** 6  
**Total Screens:** 1 (Unified Telemetry & Action Dashboard Screen with 4 View Perspectives)  
**Version:** v5.0 (Multi-View Perspectives, Decoupled Commodity Switching, Gemini 3.8/3.5/3.1 Multimodal Native Integration)

---

## 1. Executive Summary
TaniPresisi AI adalah platform agritech terintegrasi berbasis Computer Vision (Google Gemini Multimodal API: Gemini 3.8 Flash, Gemini 3.5 Flash Lite, Gemini 3.1 Pro) untuk mendiagnosa kesehatan daun tanaman perkebunan (Kelapa Sawit, Karet, Cabai, Padi, Kopi, dan tanaman kustom), menghitung dosis presisi pupuk hayati ramah lingkungan, mencegah kerusakan tanah akibat overdosis kimia, dan mengotomasi instruksi kerja lapangan (SPK) untuk mandor via WhatsApp.

Aplikasi dilengkapi dengan sistem **Multi-View Perspectives** yang memungkinkan pengguna menyesuaikan fokus kerja:
1. **🔍 Dokter Daun Saja:** Khusus diagnosis patogen daun, tingkat keparahan, dan apa yang mendesak dibutuhkan tanaman saat ini.
2. **🧪 Dosis Pemupukan Presisi:** Khusus kalkulator dosis formula hayati per pohon, kebutuhan air pelarutan, dan penghematan biaya pupuk kimia petani.
3. **📅 Perawatan & Agroklimat:** Khusus rencana aksi pemulihan 3 fase, rekomendasi jam semprot stomata, peringatan cuaca, dan SPK mandor.
4. **🌿 Lengkap (All-in-One):** Tampilan dasbor terpadu yang menampilkan seluruh modul secara komprehensif.

---

## 2. Functional Requirements Breakdown

### FR-01: Multimodal Leaf Ingestion & Gemini AI Vision Diagnosis (Gemini 3.8 / 3.5 / 3.1)
- **Objective:** Mengizinkan pengguna mengunggah foto daun tanaman perkebunan secara manual (file picker / drag-and-drop), mengambil foto langsung via kamera perangkat, atau menguji sampel terkalibrasi (pre-embedded Base64), kemudian mengirim citra ke Google Gemini Multimodal API dengan prioritas model:
  1. `gemini-3.8-flash` (Frontier Speed & Agentic Reasoning)
  2. `gemini-3.5-flash-lite` (Ultra-Low Latency & High Volume)
  3. `gemini-3.1-pro` (Deep Agronomic Reasoning & Multimodal)
  4. `gemini-2.5-flash`, `gemini-2.0-flash`, `gemini-1.5-flash` (Stable Fallbacks)
- **Actor:** Petani, Mandor Kebun, Agronomist, Juri Hackathon.
- **Inputs:** Berkas citra (JPG, PNG, HEIC, WebP) terkompresi otomatis canvas HTML5 atau Base64 pre-loaded + Gemini API Key.
- **Outputs:** Label penyakit spesifik, persentase tingkat kerusakan, skor kepercayaan AI (*Confidence Score*), bounding box deteksi visual, resep formula hayati, dan highlight khusus **"Apa yang Mendesak Dibutuhkan Tanaman Saat Ini"** (Tindakan 24-48 jam).

### FR-02: Parameter Kebun, Dynamic Eco-Dosage Calculator & Commodity Management
- **Objective:** Menghitung dosis presisi pupuk ramah lingkungan secara real-time berdasarkan komoditas terpilih dan stepper/slider jumlah pohon (10 - 500 pohon), serta mendukung penambahan/penghapusan jenis tanaman kustom (`+ Tambah Tanaman / Blok`).
- **Actor:** Petani, Mandor Kebun.
- **Inputs:** Pilihan komoditas (Sawit, Karet, Cabai, Padi, Kopi + Tanaman Kustom), stepper (`-50`, `-10`, `+10`, `+50`), slider pohon, dan harga acuan pupuk kimia.
- **Outputs:** Dosis per pohon (gram), volume pelarut air (liter), total formula ramah lingkungan (kg), dan volume larutan lapangan total.

### FR-03: Real-Time Economic & Ecological Impact Telemetry
- **Objective:** Menghitung dampak riil ekonomi (penghematan uang tunai petani dari selisih pemborosan pupuk kimia) dan dampak ekologi keberlanjutan (residu kimia nitrat/fosfat yang dicegah masuk ke tanah & aliran sungai).
- **Actor:** Sustainability Auditor, Investor, Juri Hackathon.
- **Outputs:** Angka Rupiah dihemat (`Rp xxx.xxx Dihemat`), kilogram pupuk kimia berlebih yang dicegah, mitigasi keasaman tanah, dan alignment SDGs (#12, #15, #2).

### FR-04: Precision Agronomic Advisory & Dynamic Weather Agroklimat Engine
- **Objective:** Memberikan rekomendasi jadwal waktu penyemprotan optimal berbasis kondisi stomata daun dan integrasi simulasi cuaca dinamis (Cerah Berawan, Mendung Tebal, Hujan Lebat) yang secara real-time memperbarui badge navbar, kartu risiko limpasan, dan notifikasi drawer (🔔).
- **Actor:** Petani, Mandor Kebun, Spraying Operator.
- **Outputs:** Jendela jam semprot terbaik, tingkat efisiensi penyerapan (95% vs 0%), status risiko pencucian residu kimia (85% - 99%), dan notifikasi pencegahan pemborosan.

### FR-05: 3-Phase Recovery Action Plan & Instant SPK WhatsApp Dispatch
- **Objective:** Menyusun rencana pemulihan kebun bertahap (Fase 1: 0-48 jam, Fase 2: Minggu 1-2, Fase 3: Bulan 1) dengan checkbox interaktif, kalkulasi kemajuan (%) otomatis, dan generator dokumen Surat Perintah Kerja (SPK) yang terformat rapi dan dapat disalin atau dikirim langsung ke WhatsApp Mandor Lapangan dalam 1-klik.
- **Actor:** Mandor Lapangan, Pemilik Kebun.
- **Outputs:** Checkbox progres pemulihan, teks dokumen SPK terstandarisasi, dan tautan otomatis `https://wa.me/?text=...`.

### FR-06: Multi-View Perspectives & Decoupled State Architecture
- **Objective:** Menyediakan 4 mode tampilan independen (Lengkap, Dokter Daun Saja, Dosis Pemupukan Presisi, Perawatan & Agroklimat) serta memastikan pergantian komoditas pada Panel Pengaturan Kebun tidak mereset citra daun scanner maupun hasil diagnosis AI aktif.
- **Actor:** Petani, Agronomist, Mandor, Juri.
- **Inputs:** Tombol navigasi mode tampilan, filter komoditas, tombol muat sampel daun.
- **Outputs:** Tampilan adaptif terfokus sesuai kebutuhan pengguna, independensi state scanner vs kebun.
