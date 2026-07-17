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
   address, 1 biometric") is designed to be screenshotted.
5. Below the fold: a **What can happen after upload** vs **What to do instead**
   comparison, and a disclaimer footer.

## Design notes

- **Staged simulation only.** There is no file input, no camera access, and no
  upload. All "extracted" data is fictional. The sample photos are deliberately
  simple SVG illustrations — never photorealistic imagery.
- **Signature element:** the headline redaction bar peels back to reveal
  "everything in the frame" once the final layer is exposed.
- **Accessible:** keyboard-operable, `prefers-reduced-motion` respected,
  ARIA roles on the chat log and exposure meter.
- **Responsive** down to mobile.
- **Australian English** throughout; references APPs, PDPL and GDPR.
- A light branding slot (top-right "Your logo" placeholder) is left for
  organisations to drop in their own mark.

## Customising

All copy and scenarios live in the `DATA`, `BAD_LIST` and `GOOD_LIST` objects
inside the `<script>` block of `index.html`. Add or edit a scenario by copying an
existing entry (label, caption, reply, `summary` stats, and four `layers`).
