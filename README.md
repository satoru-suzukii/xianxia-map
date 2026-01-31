# 🌌 Xianxia Infinite Realm: Procedural Map Engine

A lightweight, high-performance procedural terrain and settlement generator built entirely in vanilla **HTML5, CSS3, and JavaScript**. This engine simulates a vast, infinite cultivation world ("Xianxia") using fractal noise, multi-layered biome logic, and a persistent "Divine Sense" notebook system.

Designed as a modular core for future RPGs or browser-based cultivation games, it allows users to traverse an endless world where geography is dictated by the flow of **Qi**, **Elevation**, and **Moisture**.

---

## ✨ Key Features

* **Infinite Procedural Generation:** Uses Fractal Brownian Motion (fbm) and Bilinear Interpolation to generate seamless terrain on the fly.
* **Triple-Layer Biome Logic:** Terrain is determined by the intersection of three distinct values:
    * **Elevation (e):** Determines the transition from Abyssal Seas to Heavenly Peaks.
    * **Moisture (m):** Dictates the presence of Dune Seas (deserts) or Deep Forests.
    * **Qi Density (q):** A low-frequency noise layer that triggers rare biomes like Jade Forests or determines if a peak becomes a Volcano.
* **Settlement Engine:** Intelligent placement of Imperial Capitals, Sects, Fortresses, and Villages.
    * **Context-Awareness:** Port Cities only spawn on coastal tiles that are directly adjacent to water.
* **The Ledger (Scribe Edict):** A coordinate-based persistent notebook. Players can record the "Dao" of a specific location, leaving notes that are saved to the local session ledger.
* **Responsive "Mobile-First" Design:** Optimized for both desktop (Keyboard/WASD) and mobile (D-Pad) interaction with a sleek, dark cultivation-themed UI.

---

## 🛠 Technical Deep Dive

### The World-Gen Algorithm
The engine avoids "pure randomness" in favor of structured noise. Every tile $(x, y)$ is a result of a deterministic seed-based hash.

1.  **Smoothing:** Uses a quintic curve for interpolation to prevent "blocky" artifacts common in basic noise generators.
2.  **Octaves:** The `fbm` function layers multiple frequencies of noise, creating realistic "jagged" coastlines and mountain ranges rather than simple smooth blobs.
3.  **The "Triple Gate" Check:** Rare biomes use complex logic. For example, a **Jade Forest** requires high Moisture ($m > 0.65$), mid-range Elevation ($0.45 < e < 0.7$), and a high Qi threshold ($q > 0.75$).

### Script Constants
* **Scale (0.04):** Set to simulate a vast "10km per tile" feel.
* **Seed:** A 6-digit seed (100000–899999) that can be manually reset via reincarnation.

---

## 🎮 Controls

### Navigation
* **D-Pad / UI Buttons:** Use the UI arrows to move the "Divine Sense" across the grid.
* **Keyboard:** Supports `WASD` and `Arrow Keys` for rapid exploration.
* **Void Drift:** Teleports your consciousness thousands of miles in a random direction.
* **Reincarnate:** Generates an entirely new universe with a new seed.

### Interaction
* **Eye Icon / Enter:** Inspect and "zoom" into the current location.
* **Tile Click:** Open the **Notebook (Scribe Edict)** to view the biome description or record personal notes.

---

## 🗺 Biome Reference

| Icon | Name | Description | Logic Requirement |
| :--- | :--- | :--- | :--- |
| 🏔️ | **Heavenly Peak** | Thin, pure air. | $e > 0.79$ |
| 🌋 | **Volcano** | Magma flows and ash. | $e > 0.79$ & $q < 0.2$ |
| 🎋 | **Jade Forest** | Bamboo glowing with Qi. | High Moisture + High Qi |
| ⚓ | **Port City** | Trade hubs of the seas. | Coast ($0.35 < e < 0.38$) + Neighbor Water |
| ⛩️ | **Sect** | Centers of cultivation. | Rare Spawn ($h > 0.960$) |
| 🏜️ | **Dune Sea** | Endless golden sands. | Low Moisture ($m < 0.2$) |

---

## 🚀 Getting Started

1.  **No Installation Required:** This is a "Single File" application.
2.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/xianxia-map-engine.git](https://github.com/your-username/xianxia-map-engine.git)
    ```
3.  Open `xiaxia-map.html` in any modern web browser.

---

Made by **Satoru Suzuki**
> "The Dao that can be mapped is not the eternal Dao; yet, one must start the journey somewhere."
