# Hardware_Design - Dual-Channel P-Channel MOSFET Power Switching Circuit

**Dual-Channel P-Channel MOSFET Power Switching Circuit** — MOSFET-based high-side switching design for instantaneous power handover between primary (adapter) and backup (battery) sources. The design achieves seamless source transfer with near-zero switching delay and includes protection and filtering for reliable embedded-system operation.

---

## Key Features
- MOSFET-based high-side switching (no mechanical relays) for instant failover  
- Dual input support (e.g., 24 V adapter + battery) with priority handling  
- Schottky diode reverse-current protection and decoupling for stability  
- Compact PCB-ready schematic verified in LTspice and designed in Altium Designer  
- Use-cases: IEMS, IoT edge devices, UPS/back-up circuits, solar + battery systems

---

## Files in this repository
- `index.html` — Project landing page (animated) for quick preview and links  
- `README.md` — Project summary and instructions (this file)  
- `schematic.png` — Project schematic image (place your schematic image here)  
- `Dual_Power_Switching_Circuit.asc` — LTspice simulation file (optional)  
- `datasheet/` — (optional) folder for MOSFET, diode datasheets, BOM, and PCB gerbers  
- `report.pdf` — Project report / design notes (place your PDF here)

---

## Circuit overview (short)
The circuit uses two P-channel MOSFETs (M1, M2) as high-side switches. When the primary source is present, M1 is on and supplies the load. If the primary fails, M1 turns off and M2 immediately conducts, supplying the load from the battery. Schottky diodes prevent backfeed while RC gate networks reduce transients and ensure gate stability.

**Core components**
- P-Channel MOSFET: DMP4025LK3 (example)  
- Schottky Diode: B540C  
- Gate resistor: 4.7 kΩ  
- Decoupling capacitors: 10 µF, 1 µF

---

## How to view
1. Place your `report.pdf` and `schematic.png` in the repository root.  
2. Open `index.html` in a browser for a quick animated project page preview.  
3. To view or run the simulation, open `Dual_Power_Switching_Circuit.asc` in LTspice.

---

## Usage / Integration
- Suitable as a power front-end for embedded nodes (IEMS, sensor hubs) requiring uninterrupted operation.  
- For PCB layout: follow power routing practices (wide traces, thermal relief for power MOSFETs, proper decoupling).  
- Test with current-limited supplies before connecting real batteries. Verify thermal performance under load.

---

## Simulation & Design
- **Simulation:** LTspice (transient switching, loss & conduction analysis)  
- **Layout & PCB:** Altium Designer (component placement, thermal vias, power plane considerations)  
- **Validation:** bench testing with scope to verify switching transient and output stability

---

## References
- MOSFET and diode datasheets (see `/datasheet` if included)  
- LTspice reference examples for P-channel switching  
- Application notes for high-side MOSFET switching

---

## Author
**Pramodh R S** — Embedded Systems Engineer  
PHYTEC Embedded Pvt. Ltd — Bengaluru, India  
GitHub: https://github.com/Pramodh-RS2004

---

## License
(Include your preferred license here, e.g., MIT)
