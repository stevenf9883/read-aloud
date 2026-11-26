看圖朗讀 — 使用說明

【一】image_to_speech.py（可完全離線、可獨立使用）
  功能：圖片中的中文 → 自動朗讀
  安裝：
    1. 安裝 Python 3.9 以上
    2. pip install pytesseract pillow pyttsx3 opencv-python
    3. 安裝 Tesseract OCR 並勾選中文語言包 (chi_sim / chi_tra)
       Windows: https://github.com/UB-Mannheim/tesseract/wiki
       macOS:   brew install tesseract tesseract-lang
       Linux:   sudo apt install tesseract-ocr tesseract-ocr-chi-sim tesseract-ocr-chi-tra
  用法：
    python image_to_speech.py 圖片.png
    python image_to_speech.py --watch 資料夾
    python image_to_speech.py --camera

【二】read-aloud.html（手機網頁版）
  此檔案的辨識功能依賴 Claude 的執行環境，
  只能在 Claude 內發布的頁面中運作，單獨下載後無法辨識文字。
  請直接使用 Claude 中發布的版本。

【三】read-aloud-static.html（純靜態網頁版，可獨立使用）
  辨識改用 Tesseract.js，在瀏覽器內完成，不需任何後端，圖片不會上傳。
  用法：直接用瀏覽器開啟，或放到任何靜態主機（GitHub Pages、Netlify、公司內網 IIS 等）。
  注意：
    - 需連網：引擎與中文語言包從 jsDelivr CDN 載入，首次約 10–20MB，之後會被瀏覽器快取。
    - 朗讀使用瀏覽器內建語音 (Web Speech API)，需系統裝有中文語音。
    - 手機上使用建議放在 HTTPS 網址。
    - 辨識率不如 AI 版，拍照時請盡量對正、光線充足、文字清楚。
