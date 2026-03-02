# 🔋 Solar Panel Efficiency Simulator ☀️



<p align="center">
  <i>Pure digital logic simulation of solar panel efficiency without microcontrollers!</i>
</p>

<img width="487" height="316" alt="Screenshot 2026-03-02 122937" src="https://github.com/user-attachments/assets/61a5864e-29cc-447c-a6ec-f27e49061085" />

## 📌 Project Overview

This project simulates the efficiency of a solar panel using **pure digital logic components** in LogicWorks 5. The system models the real-world relationship between **light intensity**, **panel angle**, and **power output** — all implemented without a single line of code!

What makes this special? We built everything using counters, multiplexers, PROMs, and LEDs to demonstrate how complex calculations can be performed using fundamental digital logic building blocks.

---

## ✨ Features

### 🎛️ Hybrid Input Modes
| Mode | Description | Components |
|------|-------------|------------|
| **Binary Mode** | Manual input via DIP switches | 4 DIP switches |
| **Decimal Mode** | Step-based control via counters | Up/Down counters |
| **Mode Selection** | Seamless switching between input types | Multiplexer (MUX) |

### 💡 Smart Indicators
- 🖤 **Night Mode** - Black LED activates when light intensity = 0
- 💜 **Weak Light** - Purple LED warns when intensity is low (1–3)
- 🟩 **Ideal Angle** - Green LED for optimal angles (0°–60°)
- 🟨 **Moderate Angle** - Yellow LED for acceptable angles (60°–90°)
- 🟥 **Invalid Angle** - Red LED warning when angle > 90°

### 📊 Real-time Output
- **Two-digit decimal display** showing calculated power output
- **BCD conversion** for accurate seven-segment representation

---

## 🧠 How It Works

<p align="center">
  <b>Input → Calculate → Multiply → Convert → Display</b>
</p>

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   INPUT     │───▶│    PROM     │───▶│    PROM     │───▶│    PROM     │───▶│  7-SEGMENT  │
│ Binary/Dec  │    │ cos(angle)  │    │ Multiplier  │    │ BCD Converter│    │  DISPLAY    │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
                          │                   │                  │
                          ▼                   ▼                  ▼
                    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
                    │    LED      │    │    LED      │    │    LED      │
                    │  Indicators │    │  Indicators │    │  Indicators │
                    └─────────────┘    └─────────────┘    └─────────────┘
```

### 📐 System Flow Breakdown

1. **Input Stage**
   - User selects input mode via multiplexer
   - Binary: Direct DIP switch input
   - Decimal: Counter-based step input (increment/decrement)

2. **Cosine Calculation**
   - First PROM stores lookup table for `cos(angle) × 15`
   - Maps angle input to appropriate cosine value

3. **Power Multiplication**
   - Second PROM performs multiplication: `(light intensity) × (cosine value)`
   - Outputs 8-bit power value

4. **BCD Conversion**
   - Third PROM converts 8-bit binary to two BCD digits
   - Enables decimal display on seven-segment LEDs

5. **Visual Feedback**
   - Parallel LED indicators show system status in real-time
   - Seven-segment displays show final power output (00-99)

---

## 🛠️ Tools & Components

| Category | Components Used |
|----------|-----------------|
| **Simulation Software** | LogicWorks 5 |
| **Memory Components** | PROMs (Programmable Read-Only Memory) for lookup tables, multiplication, BCD conversion |
| **Input Devices** | DIP switches, Counters (increment/decrement) |
| **Selection Logic** | Multiplexer (MUX) for mode selection |
| **Output Devices** | 7-Segment Displays, LEDs (5 colors) |
| **Logic Elements** | Basic gates, decoders, buffers |

---

## 🚀 Expected Outcomes

✅ Accurate simulation of real-world solar panel behavior under varying conditions  
✅ Intuitive feedback through color-coded LED indicators  
✅ Real-time 2-digit decimal display of power output (00-99)  
✅ Demonstration of key digital logic concepts:
- Lookup table implementation with PROMs
- Counter-based input methods
- Multiplexer-based mode selection
- BCD conversion for display
- Parallel status indication

---

## 📚 Skills Learned

<div align="center">

| Technical Skills | Soft Skills |
|------------------|-------------|
| PROM-based lookup table design | Team collaboration |
| Digital multiplication using memory | Technical problem-solving |
| Multiplexer implementation | Circuit debugging |
| BCD to seven-segment conversion | Documentation |
| Counter circuit design | Presentation skills |

</div>

---
---

## 🖼️ Circuit Image

<p align="center">
  <img src="./assets/SolarPanelEfficiencySimulator.png" width="800" alt="Complete Circuit Design">
  <br>
  <i>Complete circuit design in LogicWorks 5</i>
</p>

---

## 🔗 Related Projects

Check out other semester projects:
- 🎮 [Coin Collector Game](./CoinCollector.md) - 1st Semester | Programming Fundamentals
- 🦥 [Slots for Sloths](./SlotsForSloths.md) - 2nd Semester | OOP
- 🔢 [NumeraX](./NumeraX.md) - 3rd Semester | COAL
- 🏃 [Maze Runner](./MazeRunner.md) - 3rd Semester | Data Structures

---

<p align="center">
  <i>Built with logic gates, PROMs, and 2 AM debugging sessions 🌙</i>
  <br>
  <i>No microcontrollers were harmed in the making of this project! ⚡</i>
</p>![Uploading Screenshot 2026-03-02 114709.png…]()

