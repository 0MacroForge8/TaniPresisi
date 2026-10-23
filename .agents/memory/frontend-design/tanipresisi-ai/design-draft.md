# Frontend Design Specification: TaniPresisi Visual Language
**Project:** TaniPresisi AI (`tanipresisi-ai`)  
**Design Standard:** Anti-AI Slop & Precision Agritech Enterprise  
**Theme:** Light Mode Default (Pure Daylight Agritech)  

---

## 1. Color Palette & 60-30-10 Distribution
- **60% Canvas / Neutral:**
  - Base Background: `#F8FAFC` (Slate 50)
  - Card Surfaces: `#FFFFFF` (Pure White) & `#F0FDF4` (Mint Tint)
  - Borders: `#E2E8F0` (Slate 200 hairline)
- **30% Structural & Ink:**
  - Primary Dark / Deep Carbon: `#022C22` (Deep Forest Carbon, AAA Contrast)
  - Secondary Deep: `#064E3B` (Structural Dark Green)
  - Muted Ink: `#475569` (Slate 600)
- **10% Brand Accent & Alerts:**
  - Active Brand Primary: `#047857` (Chlorophyll Emerald)
  - Growth Highlight: `#10B981` (Vibrant Mint)
  - Alert / Stress Warning: `#F59E0B` (Amber Warning)
  - Critical / Pathogen: `#E11D48` (Rose Pathogen Lesion)

---

## 2. Typography Hierarchy (Strict Discipline)
- **Primary Typeface (Display & Headings):** `Plus Jakarta Sans` (Font weight 600, 700, 800)
- **Body & Controls:** `Inter` (Font weight 400, 500, 600)
- **Quantitative Telemetry & SPK Monospace:** `JetBrains Mono` (Font weight 500, 700) — strictly for sensor readouts, units, prices, and code blocks.

---

## 3. Motion & Animation Standards (Anti-Slop Guardrails)
- **No Exaggerated Pulsing:** Avoid frantic flashing or heavy bouncing radar lines.
- **Refined Precision Sweep:** 1px soft emerald beam scanning with `animation: subtleSweep 3.2s ease-in-out infinite alternate`.
- **Micro-Transitions:** Smooth hardware-accelerated transforms (`transition: all 0.2s cubic-bezier(0.16, 1, 0.3, 1)`).
