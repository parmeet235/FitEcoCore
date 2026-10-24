# FitEco 🌱 — Wardrobe Carbon & Water Footprint Tracker

> **Theme Alignment:** ST-02 (Know Your Carbon) & ST-OPEN (Sustainability & Climate Tech)  
> **Pitch:** *"Fast fashion carries a massive, hidden environmental toll. FitEco visualizes the true carbon and water costs of your wardrobe, analyzes seasonal hazard levels across garments, provides automated fabric preference conclusions, and rewards you for extending garment life and choosing second-hand."*

---

## 📌 GitHub Repository Overview

- **Short Description (GitHub 'About' Box):**
  > An eco-conscious wardrobe analytics platform that calculates real CO₂e & water footprints using WRAP and Ellen MacArthur Foundation research. Features seasonal hazard spectrums, material preference conclusions, batch additions, and wear-longevity rewards.
- **Repository Topics / Tags:**  
  `sustainability` `climate-tech` `carbon-footprint` `water-footprint` `circular-fashion` `fast-fashion` `react` `typescript` `vite` `tailwindcss` `climate-action`

---

## 🌍 The Problem & The Solution

Fast fashion accounts for ~10% of global carbon emissions and is the second-largest consumer of the world's water supply. Most consumers are unaware of the cradle-to-gate impact sewn into their everyday clothes.

**FitEco** empowers individuals to:
1. **Uncover the Hidden Impact:** Instantly quantify both **CO₂ emissions (kg CO₂e)** and **virtual water consumption (Liters)** across your entire closet.
2. **Mitigate Environmental Hazard:** Automatically rank garments across seasons into **Normal**, **Little Hazardous**, and **Dangerous** environmental impact tiers via a dynamic horizontal hazard spectrum.
3. **Automate Smart Wardrobe Conclusions:** Compare logged entries to generate data-driven recommendations on which materials and pieces to wear, care for, or phase out.
4. **Reward Circularity:** Earn Eco points and status badges by opting for second-hand items (75% footprint reduction) and reaching wear milestones (30-Wear Challenge, Century Club).

---

## ✨ Key Features

- **📊 Wardrobe Impact Dashboard (CO₂e + Water Liters):**
  - Dual metrics tracking cradle-to-gate carbon (`kg CO₂e`) and embedded water (`Liters`).
  - Real-world equivalencies (trees needed for yearly offset, bathtubs of clean water, equivalent driving kilometers).
- **📦 Multi-Item Batch Entry & Custom Catalog:**
  - Add single garments with real-time impact preview.
  - Batch add multiple items at once with custom categories, materials, seasons, and quantity multipliers.
  - Curated one-click starter packs (Capsule Minimalist, Summer Thrift Haul, Winter Essentials).
- **🌡️ Seasonal Environmental Hazard Bar Graph:**
  - Dynamic horizontal bar graph for every season (**Spring, Summer, Autumn, Winter, Year-Round**).
  - Categorizes each garment into 3 calibrated readings based on carbon, water, and wear durability:
    - 🟢 **Normal (0–35%):** Low-impact, circular, or high-longevity garments.
    - 🟡 **Little Hazardous (36–68%):** Moderate impact; requires conscious maintenance and frequent wearing.
    - 🔴 **Dangerous (69–100%):** High carbon/water footprint, low-durability virgin fast fashion.
  - Interactive filters by season, hazard tier, sorting, and inline `+1 Wear` loggers.
- **🔍 Comparative Wardrobe Conclusion & Material Preferences:**
  - Automatically compares every wardrobe log entry to reveal best-performing fabrics.
  - Clear, actionable conclusions on what kind of clothes should be preferred:
    - 🥇 **#1 Preference:** Second-hand heavy garments (denim, wool coats, jackets).
    - 🥈 **#2 Preference:** Low-irrigation natural fibers (linen, organic hemp, organic cotton).
    - 🥉 **#3 Preference:** 30+ wear durable capsule staples that reduce carbon-per-wear below 0.15 kg.
    - 🔄 **#4 Preference:** Recycled technical synthetics over virgin polyesters.
  - Itemized "What to Phase Out" breakdown for high-risk virgin synthetics and single-use apparel.
- **🔄 Interactive Wear Longevity Simulator:**
  - Compare environmental amortizations: **10 wears (Fast Fashion)** vs **30 wears (Baseline)** vs **60+ wears (Slow Fashion Hero)**.
- **🏆 Circular Rewards & Milestones:**
  - Gamified achievement badges (Second-Hand Pioneer, Thrifter Elite, 30-Wear Champion, Century Club).
  - Live Eco-Points engine rewarding thrifted choices and repeat wears.
- **⚡ In-App Reset to Zero:**
  - Clean state reset to 0 items, 0 kg CO₂e, and 0 L water with an accessible, sandboxed confirmation modal.

---

## 🔬 Scientific Data & Methodology

Unlike generic apps that use placeholder values, FitEco bases its impact calculation matrix on peer-reviewed environmental life-cycle assessments:

### Data Sources
1. **WRAP (Waste & Resources Action Programme - UK):** *Valuing Our Clothes* research detailing fiber production, garment processing, and supply chain emissions.
2. **The Ellen MacArthur Foundation (EMF):** *A New Textiles Economy: Redesigning Fashion’s Future* — benchmarks for garment utilization, circular economy potential, and secondhand reuse benefits.
3. **Higg Materials Sustainability Index (Higg MSI / Cascale):** Cradle-to-gate impact factors for raw fiber production and processing across cotton, polyester, denim, wool, linen, and viscose.

### Core Assumptions
- ♻️ **75% Saved by Second-Hand:** Extending an existing garment's life via thrifting/secondhand reuse avoids ~75% of cradle-to-gate manufacturing emissions and water depletion.
- 📅 **30 Baseline Wears:** Based on WRAP and the international *#30Wears Campaign*, garments worn at least 30 times amortize their initial production footprint down to an eco-efficient threshold.
- 🌳 **21 kg CO₂e per Tree/Year:** A mature tree absorbs approximately 21–22 kg of atmospheric CO₂ annually (EPA / European Environment Agency benchmark).
- 🛁 **150 Liters per Bathtub:** Standard domestic bathtub capacity used as a relatable water equivalency metric.

---

## 🗄️ Item Data Model

Every wardrobe entry conforms to the following schema:

```typescript
interface WardrobeItem {
  id: string;               // Unique UUID or timestamp identifier
  name: string;             // Human-readable garment title (e.g., "Vintage Levi's 501")
  category: GarmentCategory;// Jeans, T-Shirt, Jacket, Dress, Sweater, Hoodie, Shorts, Shirt, Coat, Activewear
  material: GarmentMaterial;// Cotton, Denim, Polyester, Linen, Wool, Silk, Viscose, Nylon, Recycled Poly, Organic Cotton
  season: GarmentSeason;    // Spring, Summer, Autumn, Winter, Year-Round
  is_secondhand: boolean;   // True if thrifted/vintage (unlocks 75% footprint reduction)
  wears: number;            // Number of times worn (amortizes carbon & water per wear)
  footprint_kg: number;     // Cradle-to-gate CO₂ equivalent in kilograms
  water_liters: number;     // Cradle-to-gate virtual water consumption in liters
}
```

---

## 🛠️ Tech Stack

- **Framework:** React 19 (TypeScript)
- **Bundler:** Vite 8
- **Styling:** Tailwind CSS 4
- **Icons:** Lucide React
- **Animations:** Motion (Framer Motion)
- **State & Storage:** Client-side local persistence (`localStorage`) with fail-safe initialization and zero-divide safeguards.

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ or Bun
- npm / pnpm / yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/fiteco.git

# Navigate into the project directory
cd fiteco

# Install dependencies
npm install

# Start the local development server
npm run dev
```

Visit `http://localhost:3000` (or `http://localhost:5173`) in your browser.

### Building for Production

```bash
npm run build
```

---

## 📄 License

Distributed under the Apache 2.0 License. See `LICENSE` for more information.
