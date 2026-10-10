# PDF to Word Converter by NSR Space
Client-side PDF → .docx with Bengali + English OCR. No server, no API key.

## Libraries (pinned)
- PDF.js 3.11.174 (cdnjs) – text extraction + page rendering
- Tesseract.js 5.1.1 + tesseract.js-core 5.1.0 (jsDelivr), language data `ben`, `eng` from tessdata.projectnaptha.com/4.0.0
- docx 8.5.0 (jsDelivr) – Word generation

## Deploy from Android (GitHub mobile website)
1. Open github.com in your browser, sign in, tap **+ → New repository**, name it (e.g. `pdf-to-word`), choose **Public**, create.
2. Tap **Add file → Create new file**. Name it `index.html`, paste the full contents, tap **Commit changes**.
3. Repeat for `README.md` (optional).
4. Open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, tap **Save**.
6. Wait 1–2 minutes, then open `https://YOURNAME.github.io/pdf-to-word/`.
(Tip: if phone browser shows a mobile layout, use "Desktop site" for easier editing.)

## Test plan (not yet run)
English text PDF · Bengali text PDF · English/Bengali/mixed scanned PDF · multi-page · large PDF (30+ pages) · encrypted/corrupt PDF · cancel during OCR · open .docx in Word/LibreOffice/Google Docs · project URL with subpath · block a CDN and confirm the error message · PDF with mixed text/scanned pages.

## Limitations
OCR is not 100% accurate. Layout, columns, tables, handwriting and signatures are not reconstructed. Large OCR jobs may run out of memory on phones.

## Troubleshooting
- "Could not load…": CDN blocked/offline → reload, disable content blocker.
- OCR fails at start: language data download blocked → check connection, retry.
- Bengali looks wrong in Word: install/choose a Bengali font (Nirmala UI, Noto Sans Bengali); text is stored as Unicode.
- Out of memory/tab crash: tick low-resolution OCR, convert fewer pages.
- Invalid .docx: re-run; try opening in Google Docs/LibreOffice and report the error.
