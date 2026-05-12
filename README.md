# 🌀 Smart Fan Controller PCB
### Temperature-Based PWM Speed Control System

![KiCad](https://img.shields.io/badge/Designed%20with-KiCad-blue?style=flat-square&logo=kicad)
![PCB Layers](https://img.shields.io/badge/PCB-2%20Layer-green?style=flat-square)
![Input Voltage](https://img.shields.io/badge/Input-12V%20DC-orange?style=flat-square)
![Status](https://img.shields.io/badge/Status-V2%20Complete-brightgreen?style=flat-square)

A custom-designed PCB that automatically controls a 12V fan speed based on real-time temperature readings. The system combines analog sensing, power electronics, and embedded microcontroller logic into a single compact board — no external driver modules, no off-the-shelf shields.

---

## ⚙️ How It Works

```
Temperature Sensor → MCU (ADC) → PWM Signal → MOSFET Gate → Fan Motor
```

The onboard temperature sensor feeds an analog voltage into the microcontroller's ADC. The firmware maps that reading to a PWM duty cycle, which drives the gate of a logic-level MOSFET. The MOSFET switches the 12V fan rail proportionally — cooler temps → slower fan, hotter temps → full speed.

A potentiometer also allows manual override of the speed setpoint directly on the board.

---

## ✨ Features

| Feature | Detail |
|---|---|
| Temperature sensing | Analog sensor → MCU ADC |
| PWM fan control | MOSFET-driven, variable duty cycle |
| Power input | 12V DC with on-board 5V regulated logic rail |
| Manual override | Potentiometer for speed setpoint adjustment |
| Firmware flashing | ISP programming header (no external programmer board needed) |
| Status feedback | Power LED + fan activity LED (V2) |

---

## 🖨️ PCB Design Highlights

- **2-layer board** with clearly separated power and signal zones
- **Solid ground plane** on bottom layer for noise reduction and thermal relief
- **Trace widths** calculated for 12V power paths and logic-level signals separately
- **Component placement** optimized to minimize EMI between switching MOSFET and analog sensing circuitry

---

## 🔄 V2 Improvements

V1 was a proof-of-concept. V2 addressed several real issues found during bring-up:

- ✅ Added **ISP programming header** — firmware can now be flashed in-circuit
- ✅ Added **power LED** and **fan status LED** for quick visual diagnostics
- ✅ Improved **ground return paths** to reduce switching noise on the ADC input
- ✅ Rerouted power traces for cleaner layout and better thermal handling
- ✅ Reorganized component placement to physically separate analog and power sections

---

## 🗂️ Repository Structure

```
smart-fan-controller-pcb/
├── hardware/               # KiCad project files
│   ├── schematic           # Full circuit schematic (.kicad_sch)
│   ├── pcb-layout          # Board layout file (.kicad_pcb)
│   ├── gerbers/            # Production-ready Gerber files
│   └── 3d-renders/         # 3D board renders (top and bottom views)
├── docs/                   # Design notes, calculations, and references
└── README.md
```

---

## 🛠️ Tools Used

- **[KiCad](https://www.kicad.org/)** — Schematic capture and PCB layout (open-source EDA)

---

## 🚀 Getting Started

**To view the design:**
1. Install [KiCad 7+](https://www.kicad.org/download/)
2. Clone this repo: `git clone https://github.com/perfectreda/smart-fan-controller-pcb.git`
3. Open the `.kicad_pro` file inside `/hardware/`

**To manufacture the board:**
1. Navigate to `/hardware/gerbers/`
2. Submit the Gerber files to your preferred PCB fab (JLCPCB, PCBWay, etc.)
3. Standard 2-layer, 1.6mm FR4, HASL finish

**To flash firmware:**
Connect an ISP programmer (e.g. USBasp) to the on-board ISP header and flash using `avrdude` or your IDE of choice.

---

## 📸 Visuals

> *Schematic screenshots and 3D renders available in `/hardware/3d-renders/` and `/docs/`.*

---

## 👤 Author

**Larbi Mohamed Redha**  
Engineering student — Électrotechnique | Conversion d'énergie & Systèmes embarqués  
[GitHub](https://github.com/perfectreda)

---

## 📄 License

This project is open hardware. Feel free to study, modify, and build upon it. Attribution appreciated.
