# Chroma 62000P Waveform Editor (Web-based)

這是一個基於網頁的輕量化波形編輯器，專為 Chroma 62000P 系列直流電源供應器設計。
無須安裝任何軟體，支援 ISO-16750-2 等車規測試波形的視覺化編輯與 SCPI 腳本生成。

## ✨ 功能特點 (Features)
- **視覺化編輯**: 即時預覽電壓波形 (Voltage/Time Plot)。
- **SCPI 支援**: 可讀取並解析原廠格式的 `.csv` 檔案。
- **全參數調整**: 支援 Voltage, Duration, Slew Rate (V/ms), TTL 等設定。
- **程式串接**: 支援 Program Link 與 Loop Count (循環測試) 模擬。
- **一鍵導出**: 編輯完成後可直接下載 CSV，匯入 Chroma SoftPanel 使用。

## 🚀 如何使用 (Usage)
直接開啟線上版： **[點此進入編輯器](https://您的帳號.github.io/您的Repo名稱/)**

1. 點擊 **"Choose File"** 載入既有的 CSV 檔 (或點擊 **"+ New Prog"** 從零開始)。
2. 在左側面板修改電壓、時間或斜率，右側圖表會即時更新。
3. 確認無誤後，點擊 **"💾 Save CSV"** 下載檔案。
4. 將檔案匯入 Chroma 62000P SoftPanel 即可執行。

## 🛠️ 技術棧 (Tech Stack)
- HTML5 / JavaScript (ES6)
- [Chart.js](https://www.chartjs.org/) (繪圖引擎)
- [chartjs-plugin-zoom](https://www.chartjs.org/chartjs-plugin-zoom/) (縮放功能)

---
*Disclaimer: This tool is an open-source utility and is not affiliated with Chroma ATE Inc.*