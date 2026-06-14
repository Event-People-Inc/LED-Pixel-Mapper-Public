# 💡 LED Pixel Mapper (LPM)

**The ultimate workflow tool for LED technicians and video engineers.**

LED Pixel Mapper (LPM) is a comprehensive software solution designed to streamline the complex process of designing, routing, and powering LED displays. Whether you are mapping a simple 16:9 corporate screen or a massive multi-wall concert rig, LPM takes the guesswork out of data limits, power calculations, and production documentation.

---

## 🚀 What's New in v1.6.3

- **Canvas Technical Drawing Export** — A single SVG showing every wall at its exact canvas position. Includes per-wall name labels, width dimension lines, overall canvas dimension lines, a 1.8m / 6ft person silhouette for scale, and selectable page sizes from A4 to A0 (or auto-fit). Per-wall drawings also updated with position labels, port-start markers, and BU.X backup port labels
- **Data Flow & Power Flow Map Cleanup** — Circuit name now appears on the first tile only (no more cluttered repeating labels). Removed the faint glow pass from connection arrows
- **Data Port Labels CSV — Redundancy Backup Ports** — Backup / standby ports are now included in the Data Port Labels export automatically, same format as primary ports

## 🚀 What's New in v1.6.2

- **Frame Rate Selection** — Set the output frame rate per canvas: 23.98, 24, 25, 29.97, 30, 48, 50, 59.94, or 60 Hz. Affects NovaStar COEX 1G, COEX 5G, Brompton Tessera, and HELIOS capacity calculations. Togglable instantly from the Port Panel header
- **Cable Label Exports** — Two new CSV exports for on-site cable labeling. **Data Port Labels**: one row per port, both columns show `Processor  Port` — tape to both ends of the cable. **Circuit Labels**: one row per circuit — for labeling power cables. Both open directly in Excel and are formatted for standard label sheets
- **Canvas Annotations** — Right-click any empty area in Select mode to place a free-form text label on the canvas. Drag to reposition, double-click to edit, click ✕ to remove. Annotations are hidden in routing modes and can be toggled on or off in exports
- **Pure Pixel-Accurate Canvas Export** — The Canvas Export now outputs exactly `canvasWidth × canvasHeight` pixels with no footer bar — safe for direct import into any processor software for pixel mapping
- **Stable License Activation** — License no longer deactivates when the computer is renamed. Machine identity now uses a stable Windows Machine GUID instead of the hostname

## 🚀 What's New in v1.6.1

- **NovaStar COEX 5G Support** — MX6000 Pro (5G) and MX2000 Pro (5G) with CVT8-5G fiber converters and CA50E / XA50 Pro receiver cards
- **Accurate COEX 1G Capacity** — Per-tile receiver card class calculation (Enhanced vs Standard). Mixed classes on the same port handled correctly. Hard capacity stop enforced on every route
- **Receiver Card Class Badge** — Each tile profile shows a color-coded badge (Enhanced / Standard / 5G / N/A), editable at any time
- **MX40 Pro 40-Port Mode** — Now supports up to 4 CVT boxes for 40 fully routable ports
- **Cross-Wall Circuits** — A single power circuit can now span tiles across multiple walls. Click any visible tile and the wall tab switches automatically
- **Move Port Tiles** — Right-click any port to move its entire chain to another port
- **Auto-Update** — The app silently checks for updates and prompts when a new version is available
- **About Dialog** — File → About shows version, build date, and license status

---

## 🚀 Key Features

### ⚙️ Project Setup & Hardware Configuration
* **Massive Hardware Library:** Access over 500+ pre-built LED tile profiles from major brands, or create and save your own custom tile profiles.
* **Processor & Extension Integration:** Natively add popular processors including NovaStar COEX 5G (MX6000 Pro 5G, MX2000 Pro 5G with CVT8-5G), COEX 1G (MX20, MX30, MX40 Pro in 20 or 40-port mode, MX2000 Pro, MX6000 Pro), legacy NovaStar, Brompton Tessera, and Megapixie HELIOS.
* **Color Depth Flexibility:** Toggle between standard 8-bit and high-dynamic-range 10-bit color modes. Port capacities adjust automatically based on processor family and installed receiver cards.
* **Frame Rate Selection:** Set the output frame rate per canvas — 23.98, 24, 25, 29.97, 30, 48, 50, 59.94, or 60 Hz. Affects COEX 1G, COEX 5G, Brompton, and HELIOS capacity calculations. Togglable from the Port Panel header without leaving the builder.
* **Custom Resolutions:** Choose from standard resolution presets (720p up to 8K) or input custom pixel dimensions.
* **Multi-Language Support:** Fully localized in English, French, and Spanish.

### 🖥️ Workspace & Canvas Management
* **Multi-Wall Organization:** Create, rename, delete, and rearrange multiple walls using a dedicated tab system.
* **Smart Layout Tools:** Drop perfectly spaced blocks of tiles, move them with pixel-perfect accuracy using coordinate calculators, and utilize industry-standard alignment/distribution tools.
* **Grouping & Locking:** Lock tiles into place or group them into single units to prevent accidental changes during complex builds.
* **Breakaway Walls:** Build one massive layout and instantly slice it into smaller, manageable tabs using the "New Wall & Move Here" feature.
* **Bulk Tile Numbering:** Automatically number tiles (independent of data routing) in four directions with custom starting numbers.
* **Canvas Annotations:** Right-click any empty area in Select mode to place a free-form text label. Drag to reposition, double-click to edit, click ✕ to remove. Hidden automatically in routing modes.

### 🔌 Data Routing (Route Mode)
* **Accurate Port Capacity:** NovaStar COEX 1G capacity is calculated per tile based on the installed receiver card — Enhanced class (A10s Pro / A8s Pro: 494,792 px/port) or Standard class (329,861 px/port) in 10-bit mode. NovaStar COEX 5G: 2,951,200 px/port @8-bit. Mixed receiver classes on the same port are handled accurately.
* **Hard Capacity Stop:** Users are hard-blocked from routing past port capacity via both click and arrow-key routing.
* **Receiver Card Class Badge:** Each tile profile shows a color-coded badge (Enhanced / Standard / 5G / N/A) indicating which receiver card is installed. Clickable to change at any time.
* **Keyboard Routing:** Use keyboard arrow keys to rapidly route data paths across tiles, mimicking industry-standard processor software.
* **Move Port Tiles:** Right-click any port to move its entire tile chain to another port with a single action.
* **Multi-Select Wall Assignment:** Ctrl+click multiple ports, then right-click to assign them all to a wall at once.
* **Port Customization:** Rename ports, assign specific ports to specific walls, and color-code data lines for visual clarity.
* **View Toggles:** Turn connection paths, direction arrows, start/end markers, and chain labels on or off.

### ⚡ Power Distribution (Circuit Mode)
* **Socapex & Single Circuits:** Add independent circuits or drop in full 6-circuit Socapex bundles.
* **Cross-Wall Circuits:** A single circuit can span tiles across multiple walls. Click any tile visible on the canvas — including ghost outlines from other walls — and the wall tab switches automatically. Arrow keys navigate across wall boundaries when tiles are physically touching.
* **Live Load Calculations:** Automatically calculate total Wattage and Amperage in real-time, with a quick toggle for 110V vs. 220V.
* **Advanced Branching (Twofers):** Split a single circuit into Branch A and Branch B on the canvas while keeping the combined power tally accurate.
* **Connector Tracking:** Specify Edison, PowerCON, or True1 connectors for each circuit to auto-generate accurate cabling pull lists.
* **Canvas Annotation Toggles:** Toggle connection paths, direction arrows, step badges, and start/end labels independently from the Circuit Display panel.

### 🛡️ System Redundancy
* **Visual Redundancy Planner:** A dedicated, drag-and-drop interface for building out your show's safety net.
* **Port-to-Port Backups:** Drag one port onto another to instantly establish a failover line.
* **Auto-Assign Backups:** Use Split Backup or Sequential Backup buttons to auto-route all redundant ports instantly.
* **Processor Mirroring:** Drag an entire secondary processor onto your primary processor to automatically pair all corresponding outputs.

### 📄 Exports & Documentation
* **One-Click "Export All":** Generate all paperwork, maps, and reports instantly into a single ZIP file.
* **Type-Specific Annotations:** Each export type (Pixel Map, Data Flow Map, Power Flow Map) has its own independent annotation panel — toggle tile labels, chain badges, icons, legends, and wattage badges separately.
* **Pixel & Flow Maps:** Export Canvas Maps, Wall Maps, Data Flow Maps, and Power Flow Maps (with "Front View" / "Back View" watermarks).
* **Technical Drawing Export:** Generate a clean architectural SVG for each wall showing tile layout, position labels, data port annotations, and backup port labels. Or export a **Canvas Layout** drawing — all walls at their exact canvas positions on a single page, with dimension lines and a person silhouette for scale. Selectable page sizes from A4 to A0.
* **Cable Label Exports:** **Data Port Labels** CSV (one row per port, including backup ports) and **Circuit Labels** CSV — both formatted for standard label sheets, open directly in Excel.
* **Production Reports:** Generate CSV data files for inventory pulls, or export formatted HTML/PDF reports branded with your company logo.
* **Test Cards:** Export perfect-resolution PNGs or SVGs for on-site color and black-level testing.
* **Pure Pixel-Accurate Canvas Export:** The Canvas Export outputs exactly `canvasWidth × canvasHeight` pixels — safe for direct import into any processor software for pixel mapping.

### 🗂️ System & File Management
* **Auto-Update:** The app silently checks for new versions in the background. An "Update Now / Skip" prompt appears when a new version is available. Opt into automatic updates via a checkbox — off by default.
* **About Dialog:** File → About shows the current version, build date, and license status.
* **Stable License Activation:** Machine identity uses a stable Windows Machine GUID — license remains active even if the computer is renamed or the user profile path changes.
* **Undo / Redo:** Full history with Ctrl+Z / Ctrl+X keyboard shortcuts.

---

## 📺 Video Walkthrough Series

Want to see LPM in action? Check out our 7-part video walkthrough series on YouTube:

1. [Initial Setup & Licensing](https://youtu.be/uUklnGishSs)
2. [The Canvas Page Overview](https://youtu.be/_POOIHc5TeM)
3. [Select Mode & Canvas Building](https://youtu.be/0LYH_04o4KI)
4. [Routing Mode & Data Paths](https://youtu.be/pJknpON4xfM)
5. [Circuit Mode & Power Calculations](https://youtu.be/ec45uZghges)
6. [Redundancy Planner](https://youtu.be/prmH2ZN_rYw)
7. [Exports & Production Documentation](https://youtu.be/z85iOOfkedM)

---

## 🛠 Installation

Download the latest release from the [Releases](https://github.com/Event-People-Inc/LED-Pixel-Mapper-Public/releases) page, run the installer, and enter your license key via **File → Licensing**.

---

## 🤝 Feedback & Feature Requests

LPM was built *by* LED techs *for* LED techs. We are constantly updating our hardware library and adding new workflow tools.

* **Missing a Tile or Processor?** Submit a request via our [Hardware Request Form](https://forms.gle/w4mhaUq3pyUCcpoA7).
* **Found a Bug or Have a Feature Idea?** Reach out directly at [kris.siwak@eventpeople.ca](mailto:kris.siwak@eventpeople.ca).

---

🌐 **[Visit the website](https://event-people-inc.github.io/LED-Pixel-Mapper-Public/)**
🛒 **[Download on Gumroad](https://eventpeople.gumroad.com/l/LEDPixelMapper)**

© 2026 Event People Inc