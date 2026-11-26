# Borrowed Power

**This card has no battery. So how does it work?** It borrows its power from the reader.

An interactive, single-page explainer of how contactless NFC cards (transit cards, bank cards, phones) work without a battery. Built for the Global Virtual Hackathon 2026, theme *Unveiling Technology*.

- **Live site:** https://mensar10.github.io/borrowed-power/
- **Demo video:** [[link]]
- **Team:** İstikbalin Cezerileri (Istanbul)

## The idea in one sentence

The reader's magnetic field powers the chip, and the card answers by changing how much power it takes.

## What's on the page

| Section | What you do | What it explains |
|---|---|---|
| Intro | Move your pointer (the "reader") toward a card | The chip wakes up only when the reader is close |
| Journey | Scroll through one morning in Istanbul | How often we tap contactless cards every day |
| The card | Click to separate the card into layers | There is a coil and a chip inside, but no battery |
| Power | Move the card closer, step through Catch / Fill / Wake / Answer | How energy reaches the chip through the reader's field |
| Reader | Take a POS terminal apart; use the Reader lab | How the reader makes the field and "hears" the card's answer; why the amount changes the message but not the signal |
| Recap | Read a day of taps; answer the before/after question | Where else the same idea is used |

## How to run

No install, no build step. Open `index.html` in a modern browser, or visit the live site.

## How it's built

- One HTML file: plain JavaScript, SVG and `<canvas>`, no frameworks or libraries.
- One animation loop (`requestAnimationFrame`) drives every moving part.
- One shared, illustrative physics model: `powerAt(d)` gives the relative power reaching the card at distance `d` (cm), and the chip wakes above `WAKE`. The same function is used in the intro, the Power section and the Reader lab.
- `waveAt()` draws the signal shown on the Reader lab scope.
- Photos are embedded in the file as compressed WebP images (page size about 7 MB).
- Respects the `prefers-reduced-motion` setting.

## What we simplified

- Signals are slowed down; amplitudes are relative, not measured.
- The power curve is a hand-tuned, illustrative shape, not a physical law.
- The real field completes 13.56 million cycles per second.
- Bits shown in the Reader lab are illustrative, not the real encoding.
- Bank-card security (the one-time code) is shown only as an idea, not as the real algorithm.
- A phone uses its own battery for NFC.
- The reader, terminal and bank decide; the card only answers.

## Use of AI tools

[[Which tools we used, for what (code drafts, images, wording), and what we checked or rewrote ourselves.]]

**Images:** [[AI-generated / taken by the team — list per image]].

## Team

**İstikbalin Cezerileri**, Istanbul

- [[Name]] — [[role]] — [[sections of the code]]

## Sources

- NXP, PN5180 NFC reader datasheet
- NFC Forum
- ISO/IEC 14443 (the standard for contactless cards)

Thanks to Dr. Taylan Başkan (Karadeniz Technical University), who answered our questions. He did not review the site.

## License

MIT
