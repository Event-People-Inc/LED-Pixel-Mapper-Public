# 💡 LED Pixel Mapper (LPM)

**The ultimate workflow tool for LED technicians and video engineers.**

LED Pixel Mapper (LPM) is a comprehensive software solution designed to streamline the complex process of designing, routing, and powering LED displays. Whether you are mapping a simple 16:9 corporate screen or a massive multi-wall concert rig, LPM takes the guesswork out of data limits, power calculations, and production documentation.

---

## 🚀 What's New in v1.7.3 (Colour Depth, Routing Speed & Report Accuracy)

* **12-bit Colour Depth** — Full 12-bit support driven by each manufacturer's published loading charts: NovaStar COEX 1G and MCTRL4K (×48 formula), COEX 5G, Brompton Tessera (with Ultra Low Latency), and Megapixel HELIOS. The EDID exporter follows suit.
* **Nameable Ports** — Double-click any port chip to name it "Stage L" or "Main". Custom names appear on the canvas, cable labels, and every report, and survive Letters/Numbers preference switches.
* **Tab to Route** — Press Tab while routing to jump to the next port on the same processor (or next circuit in the same Soca), Shift+Tab to go back. Locked backup ports are skipped.
* **Ghost Wall Labels** — In Select mode, every wall except the one you're working on shows a name badge on each cluster of its tiles, so scattered pieces are always identifiable.
* **Duplicate Canvas** — Deep-copy a whole canvas, including every wall, tile, port, circuit and route.
* **Module Row/Column Labels** — Print each module's grid address (A1, B6…) on pixel maps to direct crew to an exact panel.
* **Processor IP Addresses** — An optional IP per processor, printed on the PDF and in its own production-CSV column.
* **Exact Tile Dimensions** — Physical sizes were previously guessed from the pitch number in a tile's name, which broke badly on names whose digits weren't the pitch (NEC LED-F019i exported 10× too large). Exact millimetres were backfilled onto ~1,785 tiles, 1,749 corrected.
* **Three-Phase Report Fix** — A 3φ distro's total in the PDF was the raw sum of every circuit rather than the per-leg load, overstating it by √3. Reports now match the Circuit panel exactly.
* **Brompton XD Box Naming Fix** — Expander box names no longer desync after delete and re-add; reports and flow maps now show "Trunk A" instead of "XD 1".
* **Project Files** — Canvas names and the project file name are now fully separate, and projects save as `.lpmap` (older `.lpmap.json` files still open).
* **Also fixed** — Circuit colours on canvas match the panel and exports, the per-wall colour picker is reachable and no longer closes mid-drag, export dialog inputs keep focus, backup markers are back on Data Flow maps, and 18 duplicate ROE entries were removed.

---

## 🚀 What's New in v1.7.1 (Bug Fixes & Refinements)

* **Mac Export Reliability** — Data and Power Flow map exports now always render in software, fixing blank/empty output that some Apple Silicon Macs produced in Dark and Light styles.
* **Redundancy Planner Rebuilt** — The old flat wall of port chips is gone. Click a processor to open a drill-down tree — output cards, then CVT boxes, then ports — and drag a whole card or CVT box onto another to back it up in one move. Cards can now be given a custom name, which carries through to the PDF report and every other export.
* **PDF Redundancy Plan Redrawn** — The Redundancy Plan page of the PDF report now mirrors the same visual tree as the planner, with color-coded port chips and backup badges, instead of a flat table of port pairs.
* **2,785 Tiles** — The built-in tile library was rebuilt from the manufacturer master sheet with corrected pixel dimensions, physical sizes, and power — every existing tile preserved, ~1,790 new panels added.
* **Edit Custom Tiles & Processors** — User Tiles and My Processors can now be edited in place, not just created. Saving/editing custom hardware is a Pro feature.
* **Rotation Shortcuts** — Cmd/Ctrl+L and Cmd/Ctrl+R rotate the current selection left/right; copy-paste now preserves tile rotation.
* **Port Naming Fix** — The Letters/Numbers preference now correctly applies to ports inside H-Series cards and COEX CVT boxes, which it previously skipped.
* **Wall Tab Scrolling** — The wall tab strip and move/copy-to-wall menus scroll properly once a project has many walls.

---

## 🚀 What's New in v1.7.0 (Massive Pre-Production Update)

* **Global Preferences & Light Mode** — Customize your UI with the highly requested Light Mode. Set default port naming schemes, choose Metric vs. Imperial units, and define custom High/Low voltages for international power calculations.
* **The "Replace Tile" Feature** — Swapping gear last minute? Right-click any tile in your profile list to instantly swap it with a different model across your entire project—without losing your data or power routing!
* **Circuit Groups & Distro Load Tracking** — Organize your Socapex and single circuits into named, nestable groups (e.g., "Distro 1"). Assign them as 3-phase or single-phase, roll up your total amp draw, and view independent 110 V / 208 V load bars per group.
* **Pro-Tier Export Engine Rebuild** — Exports now run on background web workers so your UI never freezes. PDF pixel maps pre-render in parallel so the progress bar moves from the very first step.
* **EDID Binary Exporter** — Generate a real, byte-for-byte validated EDID 1.4 binary file for any wall or canvas resolution to load directly into your media servers.
* **Tearing Test MP4 Generator** — Render an actual MP4 video of your canvas pixel map with sweeping sync lines to play on-site to spot frame-sync tears at processor seams.
* **Bulletproof Capacity Math Engine** — We've fully modeled NovaStar H-Series chassis limits, Nova LCT bounding rectangle counting, and Brompton closed-loop redundancy pairing.
* **Save Custom Hardware** — Permanently save any bespoke custom tiles or custom processors directly to your personal user library. (Built-in library also expanded to over 1,000 tiles!)
* **Group Rotation Fix** — When you select a multi-tile group and rotate it, the entire group now correctly orbits around its shared center rather than spinning individual tiles in place.
* **The Ultimate PDF Production Report** — Rebuilt from scratch to include exact X/Y wall positions, processor redundancy roles, exact port capacity percentages, full Distro phase breakdowns, and embedded technical drawings.

---

## 🚀 What's New in v1.6.3

* **Canvas Technical Drawing Export** — A single SVG showing every wall at its exact canvas position. Includes per-wall name labels, width dimension lines, overall canvas dimension lines, a 1.8m / 6ft person silhouette for scale, and selectable page sizes from A4 to A0 (or auto-fit). Per-wall drawings also updated with position labels, port-start markers, and BU.X backup port labels.
* **Data Flow & Power Flow Map Cleanup** — Circuit name now appears on the first tile only (no more cluttered repeating labels). Removed the faint glow pass from connection arrows.
* **Data Port Labels CSV — Redundancy Backup Ports** — Backup / standby ports are now included in the Data Port Labels export automatically, same format as primary ports.

*(See the Releases tab for full v1.6.x patch notes)*

---

## 🚀 Key Features

### ⚙️ Project Setup & Hardware Configuration

* **Massive Hardware Library:** Access 2,700+ pre-built LED tile profiles from major brands, or create and permanently save your own custom tile profiles (Pro).
* **Processor & Extension Integration:** Natively add popular processors including NovaStar COEX 5G/1G (MX6000 Pro, MX40 Pro) and full modular H-Series chassis (H2–H20, mixed copper/fiber cards), Brompton Tessera, and Megapixel HELIOS. Output cards can be given custom names.
* **Color Depth Flexibility:** Toggle between standard 8-bit and high-dynamic-range 10-bit color modes. Port capacities adjust automatically based on processor limits.
* **Global Customization:** Toggle between Light/Dark mode, Metric/Imperial measurement units, and localized power math limits directly from the Global Preferences menu.

### 🔌 Data Routing (Route Mode)

* **Bulletproof Port Capacity Math:** Accurately calculates Nova LCT bounding rectangles, Brompton closed-loop boundaries, and receiver card classes (Enhanced vs. Standard vs. 5G).
* **Hard Capacity Stop:** Users are hard-blocked from routing past a port's maximum pixel capacity.
* **Keyboard Routing:** Use keyboard arrow keys to rapidly route data paths across tiles, mimicking industry-standard processor software.
* **Instant Gear Swapping:** Use the "Replace Tile" feature to swap hardware models globally without rebuilding your data chains.
* **Move Port Tiles:** Right-click any port to move its entire tile chain to another port with a single action.

### ⚡ Power Distribution (Circuit Mode)

* **Circuit Groups & Distros:** Group your Socapex and single circuits into named power distros. Track total loads with independent 110 V and 208 V load bars per group — plan for any venue voltage without false warnings.
* **Cross-Wall Circuits:** A single circuit can span tiles across multiple walls. Arrow keys navigate across wall boundaries when tiles are physically touching.
* **Live Load Calculations:** Automatically calculate total Wattage and Amperage in real-time, based on your custom global voltage settings.
* **Advanced Branching (Twofers):** Split a single circuit into Branch A and Branch B on the canvas while keeping the combined power tally accurate.
* **Connector Tracking:** Specify Edison, PowerCON, or True1 connectors for each circuit to auto-generate accurate cabling pull lists.

### 🛡️ System Redundancy

* **Drill-Down Redundancy Planner:** Open a processor into a tree of output cards, CVT boxes, and ports. Drag a whole card or CVT box onto another to back it up in one move, or drag a single port for a one-off failover line.
* **Processor Mirroring:** Drag an entire secondary processor onto your primary processor to automatically pair all corresponding outputs.
* **Redundancy in Every Export:** Backup pairings flow straight into the data/power flow maps, technical drawings, and the PDF report's Redundancy Plan tree.

### 📄 Exports & Documentation

* **One-Click "Export All":** Generate all paperwork, maps, and reports instantly into a neatly organized ZIP file using background web workers to prevent UI freezing.
* **EDID & Tearing Tests:** Export byte-accurate EDID binary files for your media servers and MP4 tearing-test videos to check sync on your walls.
* **Technical Drawings:** Generate clean architectural SVGs for each wall showing tile layouts, dimensions, and port annotations.
* **Pixel & Flow Maps:** Export Canvas Maps, Wall Maps, Data Flow Maps, and Power Flow Maps (with "Front View" / "Back View" watermarks).
* **Cable Label Exports:** CSV files optimized for standard label sheets to tag both ends of your data and power cables.
* **The Ultimate PDF Production Report:** A professional, clipboard-ready report detailing wall X/Y coordinates, port usage, processor redundancy roles, and complete Distro breakdowns.

---

## 📺 Video Walkthrough Series

Want to see LPM in action? Check out our YouTube walkthrough series to master the software:

1. [Initial Setup & Licensing](https://youtu.be/uUklnGishSs)
2. [The Canvas Page Overview](https://youtu.be/_POOIHc5TeM)
3. [Select Mode & Canvas Building](https://youtu.be/0LYH_04o4KI)
4. [Routing Mode & Data Paths](https://youtu.be/pJknpON4xfM)
5. [Circuit Mode & Power Calculations](https://youtu.be/ec45uZghges)
6. [Redundancy Planner](https://youtu.be/prmH2ZN_rYw)
7. [Exports & Production Documentation](https://youtu.be/z85iOOfkedM)
8. **NEW:** [V1.7 Massive Update Overview](https://youtu.be/UldAqWeXzFw)

---

## 🛠 Installation

Download the latest release from the [Releases](https://github.com/Event-People-Inc/LED-Pixel-Mapper-Public/releases) page, run the installer, and enter your license key via **File → Licensing**.

---

## 🤝 Feedback & Feature Requests

LPM was built *by* LED techs *for* LED techs. We are constantly updating our hardware library and adding new workflow tools.

* **Missing a Tile or Processor?** Submit a request via our [Hardware Request Form](https://forms.gle/w4mhaUq3pyUCcpoA7).
* **Found a Bug or Have a Feature Idea?** Reach out directly at [kris.siwak@eventpeople.ca](mailto:kris.siwak@eventpeople.ca).

---

🌐 **[Visit the website](https://event-people-inc.github.io/LED-Pixel-Mapper-Public/)** &nbsp; 🛒 **[Download on Gumroad](https://eventpeople.gumroad.com/l/LEDPixelMapper)** &nbsp; © 2026 Event People Inc
