# 電源供應器波形工具組 (Power Supply Waveform Tools)

這是一個基於網頁的整合型工具組，專為直流電源供應器 (DC Power Supply) 設計。
目前支援 **Chroma 62000P** 與 **GW Instek PSW** 兩種系列的波形檔案格式。工程師可以透過此工具在瀏覽器中直接預覽、編輯並驗證車用電子測試波形（如 ISO-16750-2），完全無需安裝任何原廠軟體。

[**🇺🇸 English Readme**](./README.md)

## 🚀 線上使用
**[點此開啟工具入口 (Tool Portal)](https://yingchaotw.github.io/waveform-tools/)**

---

## ✨ 包含工具

### 1. Chroma 62000P 編輯器 (Editor)
專為 Chroma 62000P 系列 (List Mode / Sequence) 設計的全功能編輯器。
- **功能特點**：
  - 視覺化調整電壓 (Voltage)、時間 (Time) 與斜率 (Slew Rate)。
  - 支援程式串接 (`PROG:LINK`) 與迴圈次數 (`PROG:COUNT`) 模擬。
  - 支援暗黑模式 (Dark Mode)。
  - **匯出**：可生成符合原廠格式的 `_W_mem.csv` 檔案，直接匯入 SoftPanel 使用。

### 2. GW Instek PSW 檢視器 (Viewer)
專為 GW Instek PSW 系列設計的波形預覽工具。
- **功能特點**：
  - 讀取 PSW 格式的 CSV 檔案。
  - 智慧解析：自動跳過檔頭的註解 (memo)，抓取關鍵的 `Step` 資料列。
  - 支援預覽電壓隨時間變化的波形圖。
  - **注意**：此工具目前主要用於測試前的波形確認。

---

## 📝 支援檔案格式

### Chroma 62000P (SCPI 序列)
編輯器讀取並產生標準的 SCPI 指令列表：
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

###GW Instek PSW (CSV)檢視器會自動搜尋 `Step` 標題列，並偵測 `Time(sec)` 與 `Voltage (V)` 欄位：

```csv
memo,Sequence Example...
Cycle,1,1,7
...
Step,Point,Output,Time(sec),Voltage (V),Current (A)...
1,Start,On,10,14,MAX...
2,,On,8439,0,MAX...

```

---

##🛠️ 技術架構* **核心**：HTML5, JavaScript (ES6) - 純前端運作，資料不上傳伺服器。
* **繪圖引擎**：[Chart.js](https://www.chartjs.org/)
* **互動套件**：[chartjs-plugin-zoom](https://www.chartjs.org/chartjs-plugin-zoom/)

##⚠️ 免責聲明 (Disclaimer) 本專案為社群開發的開源工具，**與 Chroma ATE Inc. (致茂電子) 或 GW Instek (固緯電子) 無任何官方關聯**。
在實際硬體上執行高壓或大電流測試前，請務必再次確認波形設定是否安全無誤。

License [MIT](LICENSE)