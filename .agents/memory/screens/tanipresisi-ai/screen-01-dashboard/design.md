# Screen Design Specification: screen-01-dashboard
**Project:** TaniPresisi AI (`tanipresisi-ai`)  
**Screen:** `screen-01-dashboard`  
**Route:** `/`  
**Purpose:** Unified leaf diagnostic, eco-dosage calculator, impact telemetry, and field SPK dispatch.

---

## Component Breakdown & Visual Hierarchy
1. **Header Component (`HeaderNavigation`):**
   - Brand logo + title: `TaniPresisi AI` with sprout icon.
   - Live AI status indicator (`Agritech AI Model v4.2 Active`).
   - Quick navigation links (`Deteksi Daun`, `Kalkulator Dosis`, `Dampak Keberlanjutan`, `Panduan Mandor`).
   - Action controls: `🔑 Gemini API Key`, `⚡ Judge Quick-Demo`, `🔔 Notifikasi Kebun`, `❓ Panduan & FAQ`.

2. **Hero Section (`HeroSection`):**
   - Value proposition with high-contrast text.
   - Dual action CTAs: `Mulai Scan Kebun Sekarang` & `Lihat Demo Instan`.
   - 3 Telemetry chips: Accuracy (94.8%), Cost Savings (35%), Zero-Hazard (100%).

3. **Control Panel (`CommodityParameterPanel`):**
   - 5 Commodity Chips (Sawit, Karet, Cabai, Padi, Kopi).
   - Range slider for tree count / land acreage (10 - 500 pohon).
   - Price input field with dynamic Rupiah formatting.

4. **Leaf Vision Ingestion (`LeafVisionPanel`):**
   - Dual Tab Bar: `Upload Foto Daun` & `Kamera Langsung / Live Scan`.
   - Native Drag-and-Drop and File Picker (`<input type="file">`).
   - Live camera viewfinder simulation with capture trigger.
   - High-visibility button: `⚡ Gunakan Data Sampel Uji (Demo Cepat untuk Juri)`.
   - Gemini Vision AI prompt integration banner & API status indicator.

5. **Diagnostic & Impact Telemetry (`AnalysisDashboard`):**
   - AI status badge with latency readout (`1.2s`).
   - 3 Impact Cards: Leaf Health (28% damage bar), Real Financial Savings (`Rp 180.000 Dihemat`), Ecological Residue Reduction (38%).
   - Precision Eco-Dosage Panel (grams/tree & liters of water).
   - Smart Weather Window (06:30 - 09:00 WIB) + Rain Threat Warning (14:00 WIB).
   - Work-Order Box (SPK) with `Copy to WhatsApp` and `Cetak SPK Lapangan`.
