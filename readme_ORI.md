Build a Browser-Only PDF Toolkit (Privacy-First)

I want to build a modern browser-based PDF toolkit inspired by websites like Compressa, iLovePDF, Smallpdf and PDFgear.

The entire application must be 100% client-side and privacy-first.

Core Philosophy

This is NOT just another PDF website.

The biggest selling point is privacy.

Every operation must happen inside the user's browser.

Non-negotiable requirements
No backend
No server processing
No cloud uploads
No APIs for PDF processing
No user accounts
No login
No database
No cookies for uploaded files
No analytics that inspect uploaded documents
No saving any uploaded file
No storing files anywhere
No temporary server storage

Workflow:

Upload File

↓

Process Completely Inside Browser

↓

Download Result

↓

Nothing is stored

The website should repeatedly emphasize these privacy guarantees.

For example:

🔒 Your files never leave your device.

Everything is processed locally inside your browser.

No uploads. No cloud. No storage.

Upload → Process → Download → Done.

These privacy messages should appear naturally throughout the website.

Tech Stack

Use:

React
Vite
React Router
pdfjs-dist
pdf-lib

Additional libraries may be used only if needed.

Everything must run locally.

The website should be deployable as a static website on:

GitHub Pages
Vercel

No backend deployment.

Website Structure

Single website.

NOT multiple Vercel projects.

Use React Router.

Example:

/
Home

/compress

/merge

/split

/organize

/scan

Every tool should have its own clean page.

Homepage

Modern dark theme.

Simple.

Professional.

Fast.

Homepage contains cards:

📦 Compress PDF

📄 Merge PDF

✂️ Split PDF

🗂 Organize Pages

📷 Scan Document

Every card opens its own page.

Shared UI

Every tool shares:

Navigation bar

Footer

Drag & Drop upload

Progress bar

Loading animation

Download button

Consistent styling

Reusable React components

Tool 1 — Compress PDF

Build this first.

Technology

pdfjs-dist

pdf-lib

Compression Process

For every page:

Load PDF

↓

Render page

↓

Canvas

↓

Convert to JPEG

↓

Insert JPEG into new PDF

↓

Repeat

↓

Download compressed PDF

Compression Presets
Maximum

Smallest file size

Display:

"Smallest file size (72 DPI)"

Settings:

renderScale = 0.8

jpegQuality = 0.45

Balanced (Default)

Display:

"Good quality (150 DPI)"

Settings:

renderScale = 1.3

jpegQuality = 0.62

This preset should mimic Compressa's balanced compression.

High Quality

Display:

"Print Ready (300 DPI)"

Settings:

renderScale = 2.0

jpegQuality = 0.85

Minimal

Display:

"Professional (300+ DPI)"

Settings:

renderScale = 2.5

jpegQuality = 0.95

Show:

Original file size

Compressed file size

Compression %

Processing progress

Download button

Tool 2 — Merge PDF

Allow multiple PDFs.

Reorder by drag & drop.

Merge.

Download.

Everything processed locally.

Tool 3 — Split PDF

Allow:

Split every page

Split by page range

Split selected pages

Everything processed locally.

Tool 4 — Organize Pages

Allow:

Drag pages

Reorder

Delete pages

Rotate pages

Extract pages

Preview thumbnails

Everything processed locally.

Tool 5 — Scan Document

This replaces PDF-to-Image tools.

The goal is a browser-based scanner similar to CamScanner, Adobe Scan or Microsoft Lens.

Everything runs locally.

No uploads.

Workflow:

Take photo or upload image

↓

Automatically detect paper edges

↓

Perspective correction

↓

Crop

↓

Remove shadows

↓

Enhance contrast

↓

Choose filter

↓

Generate PDF

Scanner Filters

Original

Enhanced

Black & White (photocopy style)

Magic Color

The Black & White filter should produce documents that look like they were scanned on a real office scanner:

bright white background
dark black text
remove gray paper
remove yellow lighting
remove shadows
sharpen text
reduce noise

The final PDF should resemble a photocopied or professionally scanned document.

UI Requirements

Modern dark interface.

Responsive.

Minimal.

Fast.

No clutter.

Every page should feel focused.

Code Requirements

Use:

React functional components

Hooks

Async/await

Reusable components

Modular architecture

Clean folder structure

Readable code

Production-quality code

Avoid duplicated logic.

Suggested folder structure

src/

pages/
    Home
    Compress
    Merge
    Split
    Organize
    Scan

components/
    Navbar
    Footer
    UploadArea
    ProgressBar
    FileCard
    Buttons

utils/
    compress.js
    merge.js
    split.js
    organize.js
    scan.js
    pdfHelpers.js
Important

Do NOT generate everything at once.

Build the project step by step.

For every step:

Explain the architecture.
Explain why each library is used.
Explain each file before writing it.
Produce production-quality code, not a quick prototype.
Keep everything modular and scalable.

The final result should be a fast, modern, privacy-first PDF toolkit where all processing happens locally in the browser, with no uploads, no cloud processing, and no storage of user files. This privacy-first approach should be one of the application's defining features.
