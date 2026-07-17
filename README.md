# One Photo, Everything It Tells Them

An interactive privacy-awareness activity for VET/RTO compliance training and AI
data-governance thought leadership. It shows what really happens when someone
sends a sensitive photo to an AI chatbot: the friendly reply is the only part
they see, while a forensic "extraction log" reveals everything the model read
from the frame.

**Open [`index.html`](./index.html) in any browser** — that's the whole activity.
It is a single, self-contained HTML file with no build step, no dependencies, and
no network calls.

## How it works

1. **Attach** one of four staged sample photos — a passport on a desk, a home-office
   selfie, a medical letter, or a pathology work order.
2. **Send** it to the simulated assistant. A scanning animation plays over the
   photo while the assistant "thinks", then it returns a friendly, helpful reply.
3. **Reveal the extraction log.** A dark forensic panel exposes four layers in
   sequence, with a *Privacy exposure* meter climbing 0 → 100%:
   - **Layer 1 · Pixels** — everything OCR/vision reads in the frame
   - **Layer 2 · Metadata** — EXIF, GPS, device fingerprint
   - **Layer 3 · Inference** — what a model can reasonably work out
   - **Layer 4 · Persistence** — where the image and its data can end up
4. A **shareable summary card** ("This one photo exposed: 8 identifiers, 1 home
   address, 1 biometric") with its stats counting up, plus a **Download share
   card** button that exports a 1200×630 (LinkedIn-ratio) PNG.
5. Below the fold: a **What can happen after upload** vs **What to do instead**
   comparison, and a disclaimer footer.

## Signature interactions

- **Forensic exhibits.** Each sample photo is dressed as an evidence exhibit —
  corner crop-marks and an `Exhibit A · IMG_4472.jpg` tag. When the extraction
  log reveals Layer 1, **numbered redaction boxes are drawn onto the photo** and
  the matching numbers appear on the chips in the log, linking "what was read" to
  "where it was in the frame".
- **Live forensic readout.** The exposure meter and the summary stats animate
  (count up) rather than snapping, and a running "identifiers read" tally climbs
  as each layer reveals.
- **Redaction headline.** The `everything in the frame` bar peels back on the
  final reveal.
- **Scanning line** sweeps the photo during the "processing" beat before the reply.

## Brand theming

A theme switch (top-right) re-skins the whole page from a single `--brand` CSS
variable — logo wordmark, accent bar, avatar and the exported share card all
follow it. Severity colours (danger/warn) are intentionally *not* brandable so the
meaning of the colour coding never changes. Presets live in the `THEMES` object;
add a client by defining a `body[data-theme="…"]{--brand:#…}` rule and a matching
logo entry.

## Design notes

- **Staged simulation only.** No file input, no camera access, no upload. All
  "extracted" data is fictional; the sample photos are deliberately simple SVG
  illustrations — never photorealistic imagery.
- **Accessible:** keyboard-operable, `prefers-reduced-motion` respected (animations
  resolve to their final state), ARIA roles on the chat log and exposure meter.
- **Responsive** down to mobile.
- **Australian English** throughout; references APPs, PDPL and GDPR.

## Customising

All copy and scenarios live in the `DATA`, `BAD_LIST` and `GOOD_LIST` objects
inside the `<script>` block of `index.html`. Add or edit a scenario by copying an
existing entry (label, caption, reply, `summary` stats, and four `layers`). To add
the on-photo redaction boxes for a new scenario, add a matching entry to
`HOTSPOTS` (coordinates are in the SVG's 236×177 space, which maps 1:1 to the
photo frame) and an `EXHIBIT` letter.
