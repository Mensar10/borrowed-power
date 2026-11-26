# Borrowed Power

**This card has no battery. So how does it work?** It borrows its power from the reader.

An interactive, single-page explainer of how contactless NFC cards, like transit and bank cards, work without a battery. Built for the Global Virtual Hackathon 2026, theme *Unveiling Technology*.

- **Live site:** https://mensar10.github.io/borrowed-power/
- **Team:** İstikbalin Cezerileri (Istanbul)

## The idea in one sentence

The reader's magnetic field powers the chip, and the card answers by changing how much power it takes.

## What's on the page

| Section | What you do | What it explains |
|---|---|---|
| Intro | Move your pointer (the "reader") toward a card, then press "Ask the card" | The chip wakes up only when the reader is close, and the card answers by changing how much power it takes |
| A day | Scroll through one day in Istanbul | How many ordinary moments use a contactless tap |
| The card | Click to open the card layer by layer | There are a coil and a chip inside, but no battery |
| Part 1: Power | Move the card closer, step through Catch / Fill / Wake / Answer | How power reaches the chip through the reader's field |
| Part 2: Reader | Take a card terminal apart; use the Reader lab | How the reader makes the field and feels the card's answer; why the amount changes the bits but not the carrier or the power |
| Recap | Read a day of taps; reveal the answer to the opening question | Where else the same idea is used |

## How to run

No install, no build step. Visit the live site, or serve the folder (for example `python3 -m http.server`) and open `index.html`. The photos load from `img/`.

## How it's built

- One HTML file: plain JavaScript, SVG and `<canvas>`, no frameworks or libraries.
- One animation loop (`requestAnimationFrame`) drives every moving part.
- One shared, illustrative physics model: `powerAt(d)` gives the relative power reaching the chip at distance `d` (cm), where 1 means the card is resting on the reader, and the chip wakes above `WAKE`. The same function is used in the intro, the Power section and the Reader lab.
- `waveAt()` draws the signal shown on the Reader lab scope.
- Photos are separate compressed WebP files in `img/` (about 5 MB in total); the page itself is one ~100 KB HTML file.
- Respects the `prefers-reduced-motion` setting.

## What we simplified

- Signals are slowed down; amplitudes are relative, not measured.
- The power curve is a hand-tuned, illustrative shape, not a physical law.
- The real field runs at 13.56 million cycles per second; the site slows it down.
- Bits shown in the Reader lab are illustrative, not the real encoding.
- Bank-card security (the one-time code) is shown only as an idea, not as the real algorithm.
- A phone uses its own battery for NFC.
- The reader, terminal and bank decide; the card only answers.

## Use of AI tools

We used **Claude** (Anthropic) to help build the prototype (the website code) and the presentation materials (texts and the demo video), and **ChatGPT** (OpenAI) to generate the photos used in the site. We chose the topic, the explanations and the design decisions, checked the physics against the sources below, and can explain every part of the code.

**Images:** all photos in `img/` were generated with ChatGPT.

## Team

**İstikbalin Cezerileri**, Istanbul

- Eymen Efe Çetin
- Mustafa Ensar Erol

## Sources

- NXP, PN5180 NFC reader datasheet
- NFC Forum
- ISO/IEC 14443 (the standard for contactless cards)

Thanks to Dr. Taylan Başkan (Karadeniz Technical University), who answered our questions. He did not review the site.

## License

MIT
