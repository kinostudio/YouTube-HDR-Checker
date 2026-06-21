# YouTube HDR Checker

[繁體中文 (Traditional Chinese)](#youtube-hdr-檢測工具--youtube-hdr-checker) | [English](#youtube-hdr-checker)

A pure client-side web application designed to check if a video file fully meets YouTube's HDR video requirements before uploading. It parses the media metadata locally in your browser, ensuring complete privacy and fast processing—even for massive video files!

## ✨ Features

- **100% Local Processing:** Uses [MediaInfo.js](https://github.com/Borewit/mediainfo.js) compiled to WebAssembly to read metadata directly in the browser. Videos are **never** uploaded to any server.
- **Fast Chunk Reading:** Reads only the necessary file headers. A 50GB file is parsed in less than a second!
- **Accurate Standards Validation:** Verifies the three key requirements for YouTube HDR:
  - 10-bit Color Depth (or higher)
  - `BT.2020` Color Primaries
  - `HLG` or `PQ` (SMPTE ST 2084) Transfer Characteristics
- **FFmpeg Fix Suggestions:** If your 10-bit video is missing the correct color space tags (common with some cameras), the tool provides a copy-pasteable `ffmpeg` command to losslessly inject the metadata in 1 second.
- **Standalone Offline Version:** A single `.html` file generator bundles the UI, scripts, and WASM binary into one file you can use entirely offline without setting up a web server.

## 🚀 Quick Start (Web App)

Install the dependencies and run the local development server:

```bash
npm install
npm run dev
```

Build for production:

```bash
npm run build
```

## 📦 Building the Standalone Offline HTML

If you want a single `standalone.html` file that can be distributed and opened directly via `file://` in any browser:

```bash
npx tsx build_standalone.js
```
The output file will be written to `public/standalone.html`.

---

# YouTube HDR 檢測工具 | YouTube HDR Checker

這是一個純客戶端的網頁應用程式，專門用來檢測您的影片檔案是否符合 YouTube HDR 影片的嚴格標準。所有的解析作業都在您的瀏覽器端本地完成，保證極致的隱私與安全，而且無論影片檔案多大都能在瞬間完成讀取。

## ✨ 特色功能

- **100% 本地處理：** 採用 WebAssembly 編譯的 [MediaInfo.js](https://github.com/Borewit/mediainfo.js) 於瀏覽器內直接解析檔案，您的影片**絕對不會**被上傳到任何伺服器。
- **高速分塊讀取：** 只讀取檔案夾帶必要標頭的部分，50GB 的超大影片也能在一秒內解析完畢！
- **精準的 HDR 標準檢測：** 嚴格檢測 YouTube HDR 的三大要件：
  - 10-bit 色彩深度 (以上)
  - `BT.2020` 色彩原色 (Color Primaries)
  - `HLG` 或 `PQ` (SMPTE ST 2084) 轉換特性 (Transfer Characteristics)
- **FFmpeg 救回建議：** 如果您的相機拍攝了 10-bit 影片但遺失了色彩標籤，本工具會自動生成 `ffmpeg` 免轉檔指令，讓您在 1 秒內無損注入遺失的 metadata 標籤。
- **單機離線純文字版：** 提供打包腳本，可以將整個介面與 WASM 解析核心打包成單一 `standalone.html` 網頁檔，不需架設任何 Web Server，雙擊即可在斷網環境下使用。

## 🚀 快速開始 (網頁應用程式)

安裝套件並啟動本地開發伺服器：

```bash
npm install
npm run dev
```

編譯上線版本：

```bash
npm run build
```

## 📦 編譯單檔離線版 HTML

如果您希望獲得一個可以四處散佈、且點擊 `file://` 直接開啟使用的 `standalone.html` 單機擋：

```bash
npx tsx build_standalone.js
```
打包後的成品將匯出至 `public/standalone.html`。
