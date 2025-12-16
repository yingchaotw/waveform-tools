# Power Supply Waveform Tools (Web-based)

A unified, lightweight web-based toolkit designed to visualize and edit test scripts for DC Power Supplies. 
This project currently supports **Chroma 62000P** (SCPI Sequence) and **GW Instek PSW** (CSV) formats, enabling engineers to verify automotive test profiles (e.g., ISO-16750-2 starting profiles) directly in the browser without installing proprietary software.

[**🇨🇳 中文說明 (Chinese Readme)**](./README_zh.md)

## 🚀 Live Demo
**[Click here to open the Tool Portal](https://yingchaotw.github.io/waveform-tools/)**

---

## ✨ Included Tools

### 1. Chroma 62000P Editor
A full-featured **Waveform Editor** for Chroma 62000P Series (List Mode / Sequence).
- **Features**: 
  - Visual editing of Voltage, Time, and Slew Rate (V/ms).
  - Supports Program Linking (`PROG:LINK`) and Loop Counts (`PROG:COUNT`).
  - Real-time chart updates.
  - **Export**: Generates valid `_W_mem.csv` files for import into Chroma SoftPanel.

### 2. GW Instek PSW Viewer
A **Waveform Previewer** for GW Instek PSW Series.
- **Features**:
  - Parses PSW-formatted CSV files (`.csv`).
  - Intelligent header detection (automatically skips memo lines).
  - Visualizes Step-based voltage transitions.
  - **Note**: This tool currently serves as a viewer to verify waveform shapes before testing.

---

## 📝 Supported File Formats

### Chroma 62000P (SCPI Sequence)
The editor expects (and generates) standard SCPI command lists:
```csv
CONF:REM ON
PROG:SEL 1
PROG:COUNT 1
PROG:LINK 0
PROG:SEQ:VOLT 12.0
PROG:SEQ:VOLT:SLEW 10
PROG:SEQ:TIME 0.5
...

```

###GW Instek PSW (CSV)The viewer looks for the `Step` header row and automatically detects `Time(sec)` and `Voltage (V)` columns.

```csv
memo,Sequence Example...
Cycle,1,1,7
...
Step,Point,Output,Time(sec),Voltage (V),Current (A)...
1,Start,On,10,14,MAX...
2,,On,8439,0,MAX...

```

---

##🛠️ Technology Stack* **Core**: HTML5, JavaScript (ES6)
* **Visualization**: [Chart.js](https://www.chartjs.org/)
* **Interaction**: [chartjs-plugin-zoom](https://www.chartjs.org/chartjs-plugin-zoom/)
* **Styling**: CSS Variables (Dark Mode support)

##⚠️ DisclaimerThis project is an open-source utility developed by the community and is **not affiliated with, endorsed by, or connected to Chroma ATE Inc. or GW Instek (Good Will Instrument Co., Ltd).** Please ensure all waveforms are verified before running high-voltage/high-current tests on actual hardware.

License [MIT](LICENSE)