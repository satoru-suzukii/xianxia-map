# ⛩️ Xianxia: Infinite Realm Map Engine

**Made by Satoru Suzuki**

A high-performance, single-file procedural world engine designed for cultivation RPGs and immortal-hero exploration games. This engine simulates a boundless world of spirit mountains and ancient sects where every tile represents a **10x10 km area**, governed by complex Qi and elemental noise layers.

Inspired by the "cultivation" genre of web novels and games, this tool provides a foundation for building infinite wuxia-style exploration without the overhead of heavy game engines.

---

## ☯️ The Path of the Dao

Unlike standard random generators, the Xianxia Engine uses **Triple-Layer Noise Abstraction** to determine the environment:

1.  **Elevation ($e$):** Determines the physical landscape, from abyssal oceanic trenches to the highest heavenly peaks.
2.  **Moisture ($m$):** A humidity layer that dictates the difference between the golden Dune Seas and the deep, canopied forests.
3.  **Qi Intensity ($q$):** Represents the spiritual flux of the land. High $q$ values create **Jade Forests** or **Volcanoes**, while low $q$ values result in more mundane plains.

---

## ✨ Key Features 

* **🌐 Infinite Procedural Exploration:** Uses **Fractal Brownian Motion (FBM)** with 4 octaves to ensure natural terrain transitions across infinite coordinates.
* **⛩️ Sacred Settlements:** Features an intelligent spawning system for **Sects**, **Imperial Capitals**, and **Fortresses** based on regional habitability.
* **⚓ Contextual Coastal Logic:** **Port Cities** only spawn on coastal tiles (elevation 0.35 to 0.38) that are directly adjacent to ocean tiles.
* **📜 The Scroll of Truth:** A built-in coordinate-based ledger that allows players to "Scribe Edicts" on locations regarding spirit veins, rare herbs, or enemy sects.
* **💾 Persistent Save System:** Integrated `localStorage` support. Your coordinates ($X, Y$), current world seed, and all scribe edicts are automatically saved and reloaded.
* **📋 Centralized Edict Reviewer:** A dedicated interface to view all notes made across the infinite map in one chronological list for easy backtracking.
* **🔑 Custom Seed Injection:** Cultivators can manually input and **"Load"** specific world seeds, allowing for shared exploration of specific timelines.
* **⚙️ Unified System Dao:** A clean modal-based UI replaces the old action bar, housing world-reset, void-drifting, and log-management tools.
* **💯 Zero-Dependency Architecture:** One single HTML file containing all Logic (JS), Styling (CSS), and Structure (HTML).

---

## 🎮 Controls

* **Navigation:** Use `WASD` or `Arrow Keys` to move your divine sense across the realm.
* **👁️ Divine Sense (Inspect):** Click your current tile to read local environmental data and scribe notes in the **Scroll of Truth**.
* **⚙️ System Dao:** Access the system menu to save your progress, jump to new coordinates, or manage your logs.
* **✨ Void Drift:** A "Teleport" protocol that allows you to jump thousands of kilometers to a new random coordinate.
* **🎲 Reincarnate:** Permanently wipe current progress and generate a completely new world seed.

---

## 🗺️ Spirit Biome Reference

| Icon | Name | Description | Logic Condition |
| :--- | :--- | :--- | :--- |
| 🏯 | **Imperial Capital** | A vast metropolis of millions of mortals. | Very Rare ($h > 0.992$) |
| ⛩️ | **Spirit Sect** | A center of cultivation power and Qi. | Rare Spawn ($h > 0.960$) |
| 🏔️ | **Heavenly Peak** | Pure air where the snow never melts. | Maximum Elevation ($e > 0.79$) |
| 🎋 | **Jade Forest** | Bamboo groves glowing with ancient Qi. | High Moisture + High Qi |
| 🌋 | **Volcano** | High-heat zones with unstable spiritual flux. | High Elevation + Low Qi |
| ⚓ | **Port City** | Coastal trade hubs touching the Spirit Ocean. | Coastal Elevation + Water Neighbor |
| 🏡 | **Village** | Humble mortal settlements. | Frequent Spawn ($h > 0.860$) |

---

## 🚀 Deployment

1.  Download the `xianxia-map.html` file.
2.  Open it in any modern web browser.
3.  No server, build-tools, or external assets required.

---

> "The Dao that can be trodden is not the eternal Dao; the name that can be named is not the eternal name."
