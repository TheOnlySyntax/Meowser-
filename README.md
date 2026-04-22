
# 🐱 Quanta Meowser — Amplified CC1101 Module for Flipper Zero

<p align="center">
  <img src="" alt="Quanta Meowser PCB" width="700"/>
</p>

<p align="center">
  <img src="<img width="1254" height="1254" alt="image" src="https://github.com/user-attachments/assets/1b8c8e6a-ecc5-4f11-bc2f-6ef160dc4422" />
" alt="Quanta Meowser Logo" width="300"/>
</p>

<p align="center">
  <b>An open-source, amplified 433 MHz RF module for Flipper Zero — built for research, learning, and fun.</b>
</p>

---

> ⚠️ **IMPORTANT NOTICE**
> This module is a **personal, non-commercial project**. It is **not for sale**, not a finished commercial product, and comes with **absolutely no warranty**. Use it responsibly and legally. The authors take **no responsibility** for any misuse, damage, or legal issues arising from the use of this hardware.

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Hardware Components](#-hardware-components)
- [Board Layout](#-board-layout)
- [Specifications](#-specifications)
- [How It Works](#-how-it-works)
- [Compatibility](#-compatibility)
- [Usage](#-usage)
- [Legal & Disclaimer](#️-legal--disclaimer)
- [License](#-license)
- [Credits](#-credits)

---

## 🧠 Overview

The **Quanta Meowser** is a custom-designed RF amplifier module built around the **Ebyte E07-433M20S** (CC1101-based) transceiver. It is designed to extend the range and performance of Flipper Zero's built-in sub-GHz capabilities by adding a **PA (Power Amplifier)** and **LNA (Low Noise Amplifier)** stage.

This module was designed and developed by **Quante Labs** as a hobby/research project. It is **not intended for sale or mass production**.

---

## ✨ Features

- 📡 **Amplified TX/RX** — Dedicated PA and LNA stages for improved range
- 🔌 **SMA Antenna Connector** — Use any compatible 433 MHz antenna
- 💡 **Status LEDs** — Separate indicators for Power, PA, and LNA states
- 🔋 **Onboard Voltage Regulation** — LM1117 linear regulator (SOT-223) for stable 3.3V supply
- 🛡️ **Protection Diode** — SS14 Schottky diode (SOD-123) for reverse polarity protection
- 🧩 **Compact Form Factor** — Designed to fit neatly with Flipper Zero
- 🔓 **Open Hardware Concept** — Built to learn and experiment, not to sell

---

## 🔩 Hardware Components

| Component | Part | Package | Description |
|---|---|---|---|
| RF Module | E07-433M20S (CC1101) | SMD Module | Ebyte 433 MHz transceiver, 20 dBm output |
| Voltage Regulator | LM1117 | SOT-223 | 3.3V LDO linear regulator |
| Capacitor | 10uF | 0402 | Decoupling capacitor ×2 |
| Resistor (LED) | 2kΩ | 0402 | Current limiting resistor for Power LED |
| Resistor (PA) | 2kΩ | 0402 | Current limiting resistor for PA LED |
| Resistor (LNA) | 2kΩ | 0402 | Current limiting resistor for LNA LED |
| Power LED | — | 0402 LED | Power status indicator |
| LED PA | — | 0402 LED | PA (Power Amplifier) active indicator |
| LED LNA | — | 0402 LED | LNA (Low Noise Amplifier) active indicator |
| Dual MOSFET / Inverter | SN74AHC1G04DBVR | SOT-23-5 | Single inverter gate for PA/LNA control logic |
| Protection Diode | SS14 | SOD-123 | Schottky diode for reverse polarity protection |
| Antenna Connector | SMA Female | Through-hole | 50Ω SMA connector for external antenna |

---

## 🗺️ Board Layout

<img width="1710" height="920" alt="image" src="https://github.com/user-attachments/assets/e55361dd-830b-48d3-89c1-32c62cf6df27" />


> See the labeled image at the top of this README for exact component positions.

---

## 📐 Specifications

| Parameter | Value |
|---|---|
| Frequency | 433 MHz (sub-GHz ISM band) |
| RF Module | Ebyte E07-433M20S (CC1101) |
| Max TX Power | ~20 dBm (with PA) |
| Supply Voltage | 5V input (regulated to 3.3V onboard) |
| Antenna Connector | SMA Female, 50Ω |
| PCB Size | Compact (fits Flipper Zero form factor) |
| PCB Color | Blue |
| LED Count | 3 (Power, PA, LNA) |

---

## ⚙️ How It Works

1. **Power Input** — The module accepts 5V which is stepped down to 3.3V via the **LM1117** regulator. Two 10uF capacitors provide filtering and stabilization.

2. **RF Transmission (PA)** — When the CC1101 module transmits, the **PA (Power Amplifier)** stage boosts the signal, and the **LED PA** lights up to indicate active transmission.

3. **RF Reception (LNA)** — During receive mode, the **LNA (Low Noise Amplifier)** improves sensitivity for weak signals. The **LED LNA** lights up accordingly.

4. **Control Logic** — The **SN74AHC1G04DBVR** single inverter (SOT-23-5) handles switching logic between PA and LNA modes.

5. **Protection** — The **SS14 Schottky diode** protects the circuit from reverse polarity events.

6. **Antenna** — The **SMA connector** allows connection of any compatible 433 MHz antenna for flexible deployment in field tests or bench experiments.

---

## 🐬 Compatibility

- ✅ **Flipper Zero** (primary target platform)
- ✅ Compatible with any CC1101-based software running on Flipper Zero
- ✅ Works with Flipper Zero custom firmware (e.g., Unleashed, RogueMaster, Xtreme)

> **Note:** This module is designed to be used with Flipper Zero's sub-GHz application stack. Proper pin mapping and configuration may be required depending on your firmware version.

---

## 🚀 Usage

> ⚠️ **Always check local RF transmission laws before using this module.** Transmitting on 433 MHz may require a license in some countries. This module amplifies signal power — use responsibly.

1. Connect the module to your Flipper Zero via the GPIO pins.
2. Attach a compatible 433 MHz antenna to the SMA connector.
3. Power on the Flipper Zero — the **Power LED** should light up.
4. Open the **Sub-GHz** app on your Flipper Zero.
5. The **PA LED** will light up during transmission, and the **LNA LED** will light up during reception.

---

## ⚖️ Legal & Disclaimer

- 🚫 **This module is NOT for sale.** It is a personal, hobby-grade project.
- 🚫 **Do not use this module for illegal RF transmissions.** Comply with all local regulations regarding radio frequency usage.
- 🚫 **Do not use this module to interfere with, jam, or disrupt any wireless communications.** This is illegal in virtually every country.
- ✅ This module is intended **solely for research, education, and personal experimentation** within legal boundaries.
- ✅ The authors are not responsible for any consequences resulting from misuse of this hardware.
- ✅ This is an open concept hardware project shared for educational purposes only.

**By building or using this module, you agree that you are solely responsible for your actions and their legal implications.**

---

## 📜 License

This project is shared for **educational and non-commercial purposes only**.

- ❌ Not licensed for commercial use or resale
- ❌ Not licensed for production manufacturing
- ✅ Free to study, build for personal use, and learn from

If you remix or build upon this design, please credit the original authors (see below) and keep it non-commercial.

---

## 💙 Credits

This project was designed and developed with passion by:

| Role | Credit |
|---|---|
| 🛠️ Hardware Design & Development | **Quante Labs** |
| 👤 Project Lead | **@me** |
| 🤝 Contributor | **@Creativecarp606** |

Special thanks to the Flipper Zero community and everyone who contributes to open hardware research.

---

<p align="center">
  Made with ❤️ by Quante Labs — <i>Not for sale. Just for fun.</i>
</p>
