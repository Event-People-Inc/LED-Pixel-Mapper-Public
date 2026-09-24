# 💡 LED Pixel Mapper (LPM)

**The ultimate workflow tool for LED technicians and video engineers.**

LED Pixel Mapper (LPM) is a comprehensive software solution designed to streamline the complex process of designing, routing, and powering LED displays. Whether you are mapping a simple 16:9 corporate screen or a massive multi-wall concert rig, LPM takes the guesswork out of data limits, power calculations, and production documentation.

---

## 🚀 What's New in v1.8.0 (Pixel Map Editor, Resolume, Redundancy Wizard)

* **Pixel Map Editor** `Pro` — Design how your pixel maps look and reuse it across projects: parametric Dual/Triple colour with hue rotation and per-wall gradients, two uploaded images in place of the checkerboard, dial-able mosaic and X marks, a movable centre badge, restyled module labels, and a logo placed anywhere at any size. The centre badge, module labels and logo can each be switched off outright. Designs are assigned per wall from a live-thumbnail picker.
* **Resolume Export** `Pro` — Build a Resolume **Advanced Output** preset from your project. Each canvas becomes a screen, each wall a slice, placed exactly where it sits. L-shaped and irregular walls export as true Polygons; detached blocks become one slice each so a gap is never mapped as wall. Save it anywhere or install it straight into Resolume's presets folder. Verified against real Arena 7.28.0 presets.
* **Brompton Redundancy Wizard** — Build a Tessera rig's redundancy in three guided steps: Closed Loop, Processor Redundancy or Mirrored Reverse. Candidate loops come from each model's own rule, so impossible configurations never appear; a validator catches the rest and prints the fix. Every edit is **scoped to the hardware it touches** — redoing your SX40s no longer disturbs an S8 or an M2 — and the wizard names what it will remove before it does anything.
* **The Redundancy Plan List** — Every group, whatever its type, is now listed with a delete button, plus **Clear all redundancy**. Cable loops and mirrored trunks previously existed nowhere in the interface. The per-card "Clear all" buttons now really clear: they used to drop the pairings but leave the group behind, so the report kept describing redundancy that was gone.
* **Hardware Pickers** — **Library** and **Add Processor** now open proper windows. Panels are cards showing pitch, pixel count, real millimetres and power, each drawn to its own proportions. Processors are shown with **drawings of their real front panels** — all 45 models — and search matches model, range or port count ("20 ports").
* **Export Settings** — **File ▸ Export Settings…** picks exactly what a file contains: walls, profiles, annotations, processors, routing, circuits, assignments, redundancy, each canvas by name, plus your library items. Processors and routing are separate, so you can send the hardware without the patch. Dependencies are enforced so an export can never be self-inconsistent.
* **Replace Processor** — Right-click a processor and swap the model while keeping your routing, in its own dialog, with the cost shown before you commit — ports carried, tiles released, any port left over capacity.
* **Whole-Device COEX Capacity** — A controller is rated for **less than its ports add up to**: an MX40 Pro's ports total 13.2M pixels but the device stops at 9.00M at 60 Hz. Now enforced per model, by frame rate, bit depth and card class, with a device-total bar on the processor header.
* **Capacity Change Warning** — Changing bit depth or frame rate resizes every port. If that would push routed ports over, a dialog names each one — processor, port, how far over, how many tiles would come off — before anything is applied.
* **Tearing Test Animation** `Pro` — Six effects (Scan Line, Sonar Line, Screen Lines, Center Pulse, Ripple Waves), with direction, colour, opacity, speed, line size, trail length and loop count. Loops are frame-exact, so the file repeats with no visible seam all day.
* **Full-Size Wall Maps in the PDF** — Every wall page stacks its three maps full width. Portrait and square walls used to get about 42 mm each; they now get the full 273 mm.
* **Accurate Mixed-Product Canvas Drawings** — A canvas mixing LED products (a 2.6 mm header over a 3.9 mm side wall) now measures every wall with **its own pitch**, so clusters sit at true size in true relative position. Each wall is dimensioned once, W × H, instead of edge by edge.
* **Soca Renames Cascade** — Renaming a Soca renames its six circuits with it, each number staying on the same circuit. A circuit you named yourself is never clobbered.
* **Delete Confirmations Everywhere** — Walls, canvases, circuits, Socas, circuit groups, ports, processors, panel profiles and saved library items all ask first. A Soca names how many circuits go with it; a panel profile names how many tiles. **✕ now means close, a bin means delete**, consistently.
* **Processor Counts by Type** — The PDF and CSV report how many of each model the job needs, counted by model, with extension boxes tallied separately.
* **Also fixed** — Deleting a panel profile left its tiles stranded on the canvas, visible but unselectable; they now go with it and old saves heal themselves on open. Renaming a port, circuit, group or Soca now marks the project unsaved. Canvas tabs hold their position instead of jumping to the front, and the wall bar's **+** sits beside the last tab.

---

## 🚀 What's New in v1.7.4 (Field Report Fixes)

* **Free Topology (NovaStar VX Pro)** — A per-processor toggle on VX400/VX1000/VX2000 Pro. Off, a port's load is the circumscribed rectangle around its cabinets (the NovaLCT model); on, it is the actual physical cabinets, so creative and staggered walls stop wasting capacity on empty space.
* **Advanced Port Capacity Overrides** — Two opt-in toggles for when the published figures are more conservative than your rig needs: full 655,360 px network capacity on 1G ports (8-bit only), and frame-rate scaling for legacy NovaStar senders. Both off by default; neither can ever reduce a port's capacity.
* **Wall Name Badge Toggle** — The ghost wall-name badges can be switched off from the canvas toolbar, and the setting persists. They now show in all three modes rather than Select only.

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
