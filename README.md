<!-- Animated Banner -->
<h1 align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&size=32&color=00C2CB&center=true&vCenter=true&width=900&height=60&lines=⚡+Dual-Channel+P-Channel+MOSFET+Power+Switching+Circuit+⚡;Hardware+Design+%7C+Power+Electronics+%7C+Embedded+Systems" alt="Typing Animation" />
</h1>

---

## 📘 Overview
> The **Dual-Channel P-Channel MOSFET Power Switching Circuit** ensures **instantaneous and seamless power transfer** between primary (adapter) and backup (battery) sources.  
> This MOSFET-based design achieves **zero switching delay**, offering **reliable and efficient power management** for embedded and IoT systems.

This circuit eliminates mechanical relays, ensuring **noise-free, fast switching**, and **continuous power delivery** to sensitive electronic systems.

---

## ⚙️ Key Features
- ⚡ **MOSFET-based high-side switching** – instant power handover without relays  
- 🔋 **Dual power inputs** (24 V adapter + 7.6 V battery) with automatic priority handling  
- 🔄 **Zero-delay switching** using DMP4025LK3 MOSFETs  
- 🧲 **Reverse current protection** via Schottky diodes (B540C)  
- 🧠 **Stability ensured** using RC gate damping networks  
- 🧩 **Compact PCB-ready design** simulated in LTspice and designed in Altium Designer  

---

## 🧠 Circuit Overview
The design uses two P-channel MOSFETs (**M1**, **M2**) for automatic high-side switching.  
- When the 24 V source is active, **M1** conducts and powers the load.  
- If the adapter supply fails, **M1** turns off and **M2** (connected to the 7.6 V battery) activates instantly.  
- **Diodes D1 and D2 (B540C)** block reverse current and protect the sources.  
- **C1–C3** capacitors stabilize voltage transients ensuring clean output.

<p align="center">
  <img src="schematic.png" alt="Dual-Channel MOSFET Power Switching Circuit" width="700"/>
</p>

---

## 🧩 Components Used
| Component | Description | Quantity |
|------------|--------------|----------|
| DMP4025LK3 | P-Channel Power MOSFET | 2 |
| B540C | Schottky Diode | 2 |
| R1, R2 | 4.7 kΩ Resistors | 2 |
| C1, C2 | 10 µF Capacitors | 2 |
| C3 | 1 µF Capacitor | 1 |
| V1 | 24 V DC Supply | 1 |
| V3 | 7.6 V Battery | 1 |
| Load | 50 Ω Resistive Load | 1 |

---

## 🧰 Tools & Simulation
<p align="center">
  <img src="https://img.shields.io/badge/LTspice-A3001E?style=for-the-badge&logo=analog-devices&logoColor=white"/>
  <img src="https://img.shields.io/badge/Altium%20Designer-8B0000?style=for-the-badge&logo=altiumdesigner&logoColor=white"/>
  <img src="https://img.shields.io/badge/Electronics-Hardware%20Design-blue?style=for-the-badge"/>
</p>

- **Simulation Tool:** LTspice (for transient switching, delay, and voltage drop analysis)  
- **PCB Design Tool:** Altium Designer (layout optimization, component routing, and thermal considerations)  
- **Validation:** Bench-tested with oscilloscope to ensure uninterrupted power delivery  

---

## 🧾 Repository Files
| File | Description |
|------|--------------|
| `schematic.png` | Circuit schematic image |
| `Dual_Power_Switching_Circuit.asc` | LTspice simulation file |
| `report.pdf` | Detailed design and analysis report |
| `index.html` | Interactive project landing page |
| `datasheet/` | Component datasheets and PCB files |

---

## 📄 Project Report
📘 [**View Full Report (PDF)**](report.pdf)

---

## 🧪 Applications
- Industrial Energy Monitoring Systems (IEMS)  
- Embedded IoT Devices  
- Solar and Battery Power Systems  
- UPS and Backup Power Units  
- Portable Sensor Hubs  

---

## 📈 Simulation Snapshot
<p align="center">
  <img src="waveform.png" alt="Simulation Waveform" width="700"/>
</p>

---

## 👨‍💻 Author
**Pramodh R S**  
Embedded Systems Engineer – *PHYTEC Embedded Pvt. Ltd, Bengaluru*  

📬 **Contact:**  
<p>
  <a href="mailto:rspramodh5@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
  <a href="https://www.linkedin.com/in/pramodh-rs-3190692b6"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
  <a href="https://github.com/Pramodh-RS2004"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/></a>
</p>

---

## ⚙️ License
This project is open-source under the **MIT License**.  
Feel free to use, modify, and improve the design with attribution.

---

## ⭐ Acknowledgments
Special thanks to **PHYTEC Embedded Pvt. Ltd** for providing hardware and development support, and to the embedded design community for sharing valuable MOSFET switching resources.
