# Chroma 62000P Waveform Editor (Web-based)

A lightweight, web-based waveform editor designed for the **Chroma 62000P Series** DC Power Supplies. 
This tool allows engineers to visualize, edit, and generate SCPI sequence files (CSV) directly in the browser, without installing any proprietary software. It is particularly useful for creating automotive test profiles (e.g., ISO-16750-2 starting profiles).

[**🇨🇳 中文說明 (Chinese Readme)**](./Readme_zh.md)

## ✨ Features
- **Visual Editor**: Real-time voltage/time plotting with zoom and pan capabilities.
- **SCPI Parsing**: Reads and parses standard Chroma SCPI `.csv` sequence files (Program/Sequence format).
- **Full Parameter Control**:
  - Edit **Voltage**, **Duration**, and **Slew Rate** (V/ms).
  - Configure **Program Linking** and **Loop Counts** for complex testing cycles.
  - Support for **TTL** triggers.
- **One-Click Export**: Generates compliant CSV files ready for import into the Chroma 62000P SoftPanel.
- **Client-Side Only**: Runs entirely in your browser. No data is uploaded to any server.

## 🚀 Live Demo & Usage
**[Click here to open the Editor](https://<YOUR-USERNAME>.github.io/<YOUR-REPO-NAME>/)**

### How to Use
1. **Load File**: Click **"Choose File"** to load an existing `*_W_mem.csv` file, or click **"+ New Prog"** to start from scratch.
2. **Edit**: 
   - Use the left sidebar to add/remove Programs or Sequences.
   - Adjust Voltage, Time, and Slew Rate.
   - The chart on the right updates instantly to reflect your changes.
3. **Inspect**: Hover over the chart to see precise values. Use the scroll wheel to zoom in on transient edges.
4. **Export**: Click **"💾 Save CSV"** to download the modified file.
5. **Run**: Import the CSV into your Chroma SoftPanel to execute the test.

## 🛠️ Technology Stack
- **HTML5 / JavaScript (ES6)**: Core logic and UI.
- **[Chart.js](https://www.chartjs.org/)**: Rendering the interactive waveform.
- **[chartjs-plugin-zoom](https://www.chartjs.org/chartjs-plugin-zoom/)**: Enabling zoom and pan interactions.

## 📝 File Format Support
This tool supports the Chroma 62000P **List Mode / Sequence** CSV format, typically structured as:
```csv
PROG:SEL 1
PROG:COUNT 1
PROG:LINK 2
PROG:SEQ:VOLT 12.0
PROG:SEQ:VOLT:SLEW 10
PROG:SEQ:TIME 0.5
...

##⚠️ DisclaimerThis project is an open-source utility developed by the community and is **not affiliated with, endorsed by, or connected to Chroma ATE Inc.** Please ensure all waveforms are verified before running high-voltage/high-current tests on actual hardware.

---

**License**: MIT

<!-- https://www.gwinstek.com/zh-TW/products/downloadSeriesDownNew/6625/1331 -->