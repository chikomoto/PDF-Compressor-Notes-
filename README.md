# PDF-Compressor-Notes
PDF Compressor Notes

# PDF Compressor Project Prompt

I want to build a browser-only PDF compressor similar to https://compressa.vercel.app.

## Goal

Create a modern PDF compressor that runs **entirely inside the user's browser**.

The application must never upload the user's PDF to any server.

The website will be deployed on **GitHub** and **Vercel**.

Everything must work client-side only.

Privacy is the highest priority.

---

## Requirements

* Next.js (latest App Router)
* TypeScript
* Tailwind CSS
* pdfjs-dist
* pdf-lib

No backend.

No API routes.

No database.

No cloud storage.

No authentication.

No analytics that collect PDF contents.

No server-side processing.

---

## Compression Method

Replicate the behaviour of https://compressa.vercel.app as closely as possible.

Based on previous analysis:

* Render every PDF page using pdfjs-dist
* Render scale approximately **1.3**
* Convert every page into JPEG
* JPEG quality approximately **0.62**
* Rebuild a brand-new PDF using pdf-lib
* Keep all processing inside the browser
* Remove metadata
* Flatten text into images (same behaviour as Compressa)

Workflow:

PDF
→ Render page
→ Canvas
→ JPEG (quality ≈ 0.62)
→ pdf-lib
→ Download compressed PDF

---

## Privacy

The compressor must guarantee:

* Files never leave the device.
* No uploads.
* No server processing.
* No storage.
* No logging of documents.

The privacy statement should read:

> Your files never leave your device. Compression happens entirely in your browser. We do not upload, store, or retain your documents.

---

## User Interface

Modern minimal design.

Large drag-and-drop upload area.

Features:

* Drag & Drop
* Browse File button
* Progress bar
* Page count
* Original size
* Estimated compressed size
* Final compressed size
* Compression percentage
* Download button

Responsive for desktop and mobile.

---

## Compression Levels

Provide presets:

Low

* JPEG Quality 0.80
* Scale 1.5

Medium

* JPEG Quality 0.62
* Scale 1.3

High

* JPEG Quality 0.45
* Scale 1.1

---

## Nice-to-have Features

* Dark mode
* File size preview
* Cancel compression
* Multi-file queue
* Drag multiple PDFs
* Download all
* Display processing time
* Client-side only badge

---

## Performance

Optimise for:

* Large PDFs
* Low memory usage
* Progressive page processing
* Fast rendering

Avoid freezing the browser.

---

## Deliverables

Build the project step by step.

Do not generate everything at once.

For every step:

1. Explain what will be built.
2. Provide the code.
3. Explain where each file belongs.
4. Wait until that step is complete before moving on.

Start from creating the project using:

npx create-next-app@latest

Then continue until the application is production-ready.

---

## Deployment

Finally:

* Push to GitHub
* Deploy on Vercel
* Verify that all PDF processing occurs entirely in the browser
* Confirm there are no network requests containing PDF data

---

## Future Improvements

After the basic version works, help improve compression quality by:

* Detecting image-heavy vs text-heavy PDFs.
* Compressing only embedded images when possible.
* Preserving selectable text when appropriate.
* Matching or exceeding Compressa's output quality while keeping similar file sizes.

