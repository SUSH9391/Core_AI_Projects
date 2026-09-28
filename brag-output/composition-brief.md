# Hyperframes Composition Brief: Core AI Projects

## Objective
Create a short launch-style brag video for Core AI Projects.

## Output
- Composition directory: `brag-output/composition/`
- Rendered video: `brag-output/brag.mp4`
- Format: landscape — 1920x1080
- Duration: 18 seconds

## Source Material
- Project root: `C:\Users\sushm\desktop\Core_AI_Projects`
- Primary files read: `README.md`, `digit_recognition_lenet.ipynb`, `Transfer_learning/transferlearning.ipynb`
- Product name: Core AI Projects
- Tagline / strongest claim: "99% accuracy on MNIST with LeNet" and "Transfer learning reduces training time from months to minutes"
- Key UI or visual moment to recreate: LeNet architecture diagram, training accuracy plot, side-by-side bee/ant image classification
- Copy that must appear verbatim:
  - LeNet
  - MNIST
  - Transfer Learning
  - 99% accuracy

## Creative Direction
- Tone preset: polished
- Creative direction: clear educational demonstration of powerful ML techniques
- Interpretation: Polished tone means smooth pacing, elegant transitions, minimal but effective SFX, focus on clarity and educational value. Avoids hype, emphasizes clean visuals and readable text.
- Angle: From brag-plan.md: clear educational demonstration of powerful ML techniques
- Hook: First 2-3 seconds: black screen with white text "What if I told you..." then cut to MNIST digit being classified by LeNet with text overlay "99% accuracy with 20 lines of code?"
- Outro / punchline: Final line: "Core AI Principles: From foundations to cutting-edge"
- Avoid:
  - Generic SaaS language like "streamline your workflow"
  - Abstract filler visuals (e.g., generic neural network cartoons not from the project)
  - Unrelated visual redesign (e.g., changing the color scheme to something not in the notebooks)

## Visual Identity
- Background: #f8f9fa (light gray, clean and professional)
- Text: #212529 (dark gray for primary text)
- Accent: #0d6efd (blue for highlights and key elements)
- Display font: Inter (or system sans-serif) for headings and body
- Body font: Courier New (monospace) for code snippets and technical terms
- Visual references from the project:
  - LeNet architecture diagram (layers: Conv2d, MaxPool2d, Linear)
  - MNIST digit grid (10 handwritten digits 0-9)
  - Training loss/accuracy plots (loss decreasing, accuracy increasing to 99%)
  - Bee vs ant images with classification confidence scores

## Storyboard
Use the storyboard in `brag-output/brag-plan.md` as the creative contract.

Scene summary:
1. Hook — 3s — Black screen with text "What if I told you..." then MNIST digit classification by LeNet, overlay "99% accuracy with 20 lines of code?"
2. LeNet Reveal — 5s — LeNet architecture diagram lighting up layer by layer, transition to training loss/accuracy graphs, accuracy counter ticking up to 99%
3. Transfer Learning Highlights — 6s — Split screen bee/ant images, ResNet18 model loading progress bar, rapid fine-tuning loss drop, final classifications "BEE: 96%" / "ANT: 92%"
4. Punchline/Outro — 4s — Black screen with centered text "Core AI Principles" and subtitle "From foundations to cutting-edge", small logo "Core_AI_Projects"

## Audio
- Audio role: warm corporate bed
- Audio arc: Starts calm, builds slightly during LeNet section, steady during transfer learning, resolves with soft ending
- Music: happy-beats-business-moves-vol-1-by-ende-dot-app.mp3
- Music treatment: Volume 0.35, fade out over last 1 second
- Music cue guidance: Use bundled preset at `brag-output/composition/assets/music/happy-beats-business-moves-vol-1-by-ende-dot-app.music-cues.json` (or extract via analyze_music_cues.py if needed)
- Audio-reactive treatment: subtle; use music RMS/bass to make subtle glow on accuracy numbers and classification confidence indicators
- Audio-coupled moments:
  - Scene 2 — accuracy counter increment — visual glow on numbers synced to bass RMS
  - Scene 3 — classification confidence appearance — SFX: interface/bong_001.ogg for each classification
- SFX selection guidance: For polished tone, use 2-3 very subtle SFX. Use interface/bong_001.ogg for soft accent, interface/drop_001.ogg for gentle reveal, impactBell_heavy_000.ogg for major payoff.
- Exact SFX choice: Hyperframes should choose filenames, timestamps, density, and volume based on the implemented animation (guidance: use bong_001 for model loading, drop_001 for accuracy plot reveal, impactBell_heavy for final classifications)
- Audio files: Copied music and SFX into `<output-dir>/composition/assets/`

## Hyperframes Instructions
Load the composition-building Hyperframes domain skills — `hyperframes-core` (composition contract + `data-*` timing), `hyperframes-animation` (motion), `hyperframes-creative` (design spec, beats, audio-reactive), `hyperframes-keyframes` (seek-safe keyframes), and `hyperframes-cli` (lint/check/render). /brag is its own workflow: do not enter the `hyperframes` entry-point intent interview and do not route into its generic promo / launch-video workflow. Prefer native Hyperframes conventions over anything in `/brag`.

Requirements:
- Show at least one real UI, copy, or visual element from the source project (we show LeNet diagram, MNIST digits, bee/ant images from notebooks)
- Keep all text readable in the final render (minimum 0.8s for labels, 0.3s per word for sentences)
- Keep the video within 15-25 seconds (our storyboard sums to 18s)
- Include the planned music/SFX layer unless audio was explicitly disabled or documented as intentionally silent (music and SFX are included)
- Treat `/brag` audio notes as guidance, not a fixed cue sheet. Choose SFX after the visual animation exists.
- Treat music cue metadata as optional timing hints. Hyperframes decides exact animation timing and should ignore cues that hurt readability, scene pacing, or the product story.
- Major reveals may move toward nearby strong cues within about 0.15s. Smaller entrances may align to nearby beat points within about 0.10s. Use only 1-3 strong cue locks in a 15-25s video unless the edit clearly benefits from more.
- Use SFX to support motion and interaction: card sounds for card-like reveals, short announcement cues for major payoffs, key/click sounds for text or user actions, and restraint when the edit is already busy.
- Honor planned music treatment such as fade-outs, ducking, beat-aligned reveals, or letting a final SFX ring over the music, using the best Hyperframes-supported implementation.
- When music is present and the treatment is not `none`, consider Hyperframes audio-reactive workflow: extract audio data and use RMS/frequency bands for subtle, brand-specific motion. Good targets are glow, depth, background warmth, card presence, title emphasis, or other existing visual elements. Avoid waveform/equalizer visuals, musical-note graphics, generic particle systems, strobing, or heavy pulsing.
- Use local assets for audio and any required runtime/media dependencies when possible.
- Run `hyperframes check` before render — it is brag's single gate.