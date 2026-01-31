🌌 Xianxia Infinite Realm: Procedural Map Engine
A lightweight, high-performance procedural terrain and settlement generator built entirely in vanilla HTML5, CSS3, and JavaScript. This engine simulates a vast, infinite cultivation world ("Xianxia") using fractal noise, multi-layered biome logic, and a persistent "Divine Sense" notebook system.
Designed as a modular core for future RPGs or browser-based cultivation games, it allows users to traverse an endless world where geography is dictated by the flow of Qi, Elevation, and Moisture.
✨ Key Features
 * Infinite Procedural Generation: Uses Fractal Brownian Motion (fbm) and Bilinear Interpolation to generate seamless terrain on the fly.
 * Triple-Layer Biome Logic: Terrain is determined by the intersection of three distinct values:
   * Elevation (e): Determines the transition from Abyssal Seas to Heavenly Peaks.
   * Moisture (m): Dictates the presence of Dune Seas (deserts) or Deep Forests.
   * Qi Density (q): A hidden stat that triggers rare biomes like Jade Forests or determines if a peak becomes a Volcano.
 * Settlement Engine: Intelligent placement of Imperial Capitals, Sects, Fortresses, and Villages.
   * Context-Awareness: Port Cities only spawn on coastal tiles that are directly adjacent to water.
 * The Ledger (Scribe Edict): A coordinate-based persistent notebook. Players can "record the Dao" of a specific location, leaving notes that are saved to the local session ledger.
 * Responsive "Mobile-First" Design: Optimized for both desktop (Keyboard/WASD) and mobile (D-Pad) interaction.
🛠 Technical Deep Dive
The World-Gen Algorithm
The engine avoids "pure randomness" in favor of structured noise. Every tile (x, y) is a result of a deterministic seed-based hash.
 * Smoothing: Uses a quintic curve for interpolation to prevent "blocky" artifacts common in basic noise generators.
 * Octaves: The fbm function layers multiple frequencies of noise, creating realistic "jagged" coastlines and mountain ranges rather than simple smooth blobs.
 * The "Triple Gate" Check: Rare biomes use complex logic. For example, a Jade Forest isn't just a forest; it requires high Moisture, mid-range Elevation, and a high Qi threshold.
Script Constants
 * Scale (0.04): Set to simulate a "10km per tile" feel.
 * Seed (6-digit): Can be manually shared between players to explore the exact same universe.
🎮 Controls
Navigation
 * D-Pad / Buttons: Use the UI arrows to move.
 * Keyboard: Supports WASD and Arrow Keys.
 * Void Drift: Teleports your consciousness thousands of miles in a random direction.
 * Reincarnate: Generates an entirely new universe with a new seed.
Interaction
 * Eye Icon / Enter: Inspect the current location.
 * Tile Click: Open the Notebook (Scribe Edict) to view the biome description or record personal notes.
🗺 Biome Reference
| Icon | Name | Description | Requirements |
|---|---|---|---|
| 🏔️ | Heavenly Peak | Pure air, high Qi. | Max Elevation |
| 🌋 | Volcano | Unstable Qi and magma. | Max Elevation + Low Qi |
| 🎋 | Jade Forest | Ancient Qi-rich groves. | High Moisture + High Qi |
| ⚓ | Port City | Trade hubs of the seas. | Coastal Tile + Water Neighbor |
| ⛩️ | Sect | Centers of power. | Rare Settlement Spawn |
| 🏜️ | Dune Sea | Golden sands. | Low Moisture |
🚀 Getting Started
 * No Installation Required: This is a "Single File" application.
 * Clone the repository:
   git clone https://github.com/your-username/xianxia-map-engine.git

 * Open xiaxia-map.html in any modern web browser (Chrome, Firefox, Safari, or Edge).
🍱 Future Roadmap
 * Local Storage Persistence: Save the ledger and current coordinates to the browser's localStorage.
 * Fog of War: Hide tiles until the player’s "Divine Sense" (coordinates) reaches them.
 * Interactive Events: Add a "Cultivate" button that triggers random encounters based on the tile's Qi density.
"The Dao that can be mapped is not the eternal Dao; yet, one must start the journey somewhere."
