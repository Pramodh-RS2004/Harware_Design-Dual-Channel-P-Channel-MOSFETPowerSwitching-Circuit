

<h1 align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Arial&size=30&color=F7931A&center=true&vCenter=true&width=900&height=60&lines=⚡+Power+Switching+Circuit+w%2F+P-Channel+MOSFETs+⚡;Hardware+Design+%7C+Power+Electronics+%7C+Embedded+Systems" alt="Typing Animation" />
</h1>

---

## 💡 Project Overview
> The **Dual-Channel P-Channel MOSFET Power Switching Circuit** ensures **instantaneous and seamless power transfer** between primary (adapter) and backup (battery) sources. This MOSFET-based design achieves **zero switching delay**, offering **reliable and highly efficient power management** for embedded and IoT systems.

This circuit eliminates mechanical relays, guaranteeing **noise-free, ultra-fast switching**, and **continuous power delivery** to sensitive electronic loads, making it ideal for critical backup applications.

---

## ⚙️ Key Features & Technical Specifications

| Feature | Description | Benefit |
| :--- | :--- | :--- |
| ⚡ **Zero-Delay Switching** | Utilizes **DMP4025LK3 P-Channel MOSFETs** for high-side switching. | Ensures **uninterrupted power** during source failure. |
| 🔋 **Dual Input Priority** | Automatically prioritizes the **24 V DC Adapter** over the **7.6 V Battery**. | Maximizes battery life and system reliability. |
| 🛡️ **Reverse Current Protection** | Integrated **Schottky Diodes (B540C)** on both channels. | Prevents sources from charging/discharging each other, protecting the power supply. |
| 🧠 **Gate Stability** | Includes dedicated **RC Gate Damping Networks** (R1, R2). | Minimizes transient ringing and ensures stable switching transitions. |
| 🛠️ **Form Factor** | **Compact PCB-ready design** verified with simulation and bench testing. | Suitable for integration into small-scale embedded enclosures. |

---

## 🧠 Circuit Schematic & Operation
The design employs two P-channel MOSFETs (**M1**, **M2**) for automatic high-side switching on the positive rail.

- **Primary Source (24 V Adapter):** When active, this higher voltage source biases **M1** ON, powering the load.
- **Backup Source (7.6 V Battery):** The lower voltage source remains OFF as long as 24 V is present.
- **Power Failure:** If the 24 V adapter fails, **M1** rapidly turns OFF, and **M2** (connected to the battery) activates instantly, ensuring **seamless power handover**.
- **Diodes D1 and D2 (B540C)** provide necessary isolation and blocking of reverse current paths.
- **C1–C3** capacitors manage load voltage stability and filter transients.

<p align="center">
  <img src="dual switching circuit.png" alt="Dual-Channel MOSFET Power Switching Circuit" width="700" style="border: 1px solid #ddd; border-radius: 4px; padding: 5px;"/>
</p>

---





---

## 📦 Components Used
| Component | Device | Purpose | Datasheet |
| :--- | :--- | :--- | :--- |
| **M1, M2** | DMP4025LK3 | P-Channel Power MOSFET (Switching) | [Link to Datasheet](datasheet/DMP4025LK3.pdf) |
| **D1, D2** | B540C | 40V, 5A Schottky Diode (Isolation) | [Link to Datasheet](datasheet/B540C.pdf) |
| **R1, R2** | 4.7 kΩ | Gate Damping / Biasing Resistors | |
| **C1, C2** | 10 µF | Input/Output Decoupling | |
| **V1** | 24 V DC | Primary Power Supply | |
| **V3** | 7.6 V DC | Backup Battery Supply | |
| **Load** | 50 Ω | Resistive Load | |

---

## 🛠️ Tools & Technologies
<p align="center">
  <img src="https://img.shields.io/badge/LTspice-A3001E?style=for-the-badge&logo=analog-devices&logoColor=white"/>
  <img src="https://img.shields.io/badge/Altium%20Designer-8B0000?style=for-the-badge&logo=altiumdesigner&logoColor=white"/>
  <img src="https://img.shields.io/badge/Verification-Bench%20Testing-green?style=for-the-badge"/>
</p>

* **Simulation & Analysis:** LTspice (used for transient switching, delay, and voltage drop analysis).
* **PCB Design:** Altium Designer (used for layout optimization, component routing, and thermal management).
* **Validation:** Bench-tested with an oscilloscope to confirm uninterrupted power delivery under stress.

---


---

## 🚀 Potential Applications
The reliable, zero-delay switching makes this circuit ideal for systems where power continuity is critical.

* **Embedded IoT Devices:** Ensuring sensors and microcontrollers remain powered during network drops or power outages.
* **Industrial Energy Monitoring Systems (IEMS):** Maintaining continuous logging and data acquisition.
* **Uninterruptible Power Supply (UPS) Units:** Used as a solid-state switch in low-power UPS designs.
* **Portable Sensor Hubs:** Seamless transition between external power and internal battery.

---

## 👨‍💻 Author & Contact
**Pramodh R S**  
Embedded Systems Engineer – *PHYTEC Embedded Pvt. Ltd, Bengaluru*  

| Platform | Link |
| :--- | :--- |
| 📧 Email | <a href="mailto:rspramodh5@gmail.com">rspramodh5@gmail.com</a> |
| 🔗 LinkedIn | <a href="https://www.linkedin.com/in/pramodh-rs-3190692b6">Pramodh R S</a> |
| 🐙 GitHub | <a href="https://github.com/Pramodh-RS2004">@Pramodh-RS2004</a> |

---

## 📝 License
This project is open-source and available under the **MIT License**.

> Feel free to use, modify, and improve the design with appropriate attribution.

## ⭐ Acknowledgments
Special thanks to **PHYTEC Embedded Pvt. Ltd** for providing hardware and development support, and to the embedded design community for sharing valuable MOSFET switching resources.
