# Odyssey Educational Foundation — Automated Newsletter System

This system reproduces the **August newsletter (1).pdf** sample **pixel-for-pixel in structure** but makes every image and text region editable and uploadable. Colours from the sample are locked as defaults.

## Features (per your requirements)

- **First page uploads** — banner hero, feature image (top-right), and the 3 tiles (Events / Volunteer/Intern Spotlight / Stories of impact) each have their own image upload. Month label (`August Edition`) is a single field that **auto-syncs to every page header**.
- **Report / document upload** — for Events, Volunteer/Intern Spotlight, and Impact Story there is a **drag-and-drop** zone for `.docx / .pdf / .txt`:
  - Drop a report containing a Title, summary, and images → the system auto-creates/fills the corresponding page(s).
  - Images embedded in `.docx` are extracted automatically as `img1` / `img2`.
  - Expected doc structure: first line = title, rest = body — or labelled fields like `Title: ...` / `Summary: ...` / `Name: ...`.
- **Icons / elements / graphics per page** — every page (cover + each event + volunteer + impact + opportunities + closing) has a dedicated **Icon/Graphic upload** slot. Uploaded PNGs/SVGs with transparency work best.
- **Colours** — sample palette locked: green `#3EAE5B`, orange `#F5822A`, page blue `#BFE4F7`, card light `#EAF6FD`. Editable but with a “Reset to sample colours” button.
- **Canva-editable export** — `Export to Canva (.pptx)` generates a **PowerPoint** file (via PptxGenJS) that is **100% editable in Canva**:
  1. Click Export → `.pptx` downloads.
  2. In Canva: `Create a design → Import file → select .pptx`. Every text box and image becomes movable/editable.
  3. Also includes `Export PDF` for print/share, plus Save/Load Project (`.json`) for reuse.

## How to run

Just open `index.html` — it is a single-file, offline-capable app (needs internet once for CDN libraries: pptxgen, html2pdf, mammoth, pdf.js).

```
odyssey-newsletter-system/
  index.html              ← open this
  August newsletter sample.pdf
  README.md
```

No build step, no server required.

## Workflow

1. Set **Month / Year** (or use the month picker).
2. Upload **cover images** (banner + feature + 3 tiles).
3. For each event: **drop the event report** or fill manually + upload `Image 1` / `Image 2` + per-page icon/graphic.
4. Drop volunteer / impact reports the same way (or fill manually + photo).
5. Add opportunities links.
6. Upload closing logo if needed.
7. Preview on the right updates live — exactly as the PDF sample layout.
8. `Export to Canva (.pptx)` → Import into Canva. Done.

## Canva note

Canva does not have a direct “push” API for free accounts, so the `.pptx` import is the official Canva-supported editable path. For Canva Teams with API access you can also upload the .pptx via Canva Connect — the generated file is already in the correct A4 vertical (7.5×10 in) format so nothing shifts.

## Fidelity

The preview and PPTX use the same grid as the sample: blue page background, 2px orange rounded-card border, green/orange/sky headers, Montserrat headings, 11–12pt body, and the exact page order: Cover → Events (one slide per event, 4 by default) → Volunteer Spotlight → Impact Story → Opportunities → Closing/Thank You. Add/remove events freely — pagination adjusts automatically.
