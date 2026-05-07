# Tayler Made Hair — site

A two-page editorial site for Tayler Made Hair (Nashville).
Static HTML + CSS + a tiny bit of vanilla JS. No build step.

```
tayler_made_hair_site/
├── index.html       Home — hero, about, signatures, portfolio, visit/book
├── services.html    Full services menu with prices and images
├── styles.css       All the design
├── script.js        Sticky nav, mobile menu, scroll reveals
└── images/          Hero + portfolio images (swap with Tayler's real work)
```

## Run it locally

Easiest way (any terminal in this folder):

```bash
python3 -m http.server 5173
```

Then open <http://localhost:5173>.

(Just opening `index.html` directly in the browser also works, but a
server is closer to how it will behave when deployed.)

## Swap in real portfolio images

The site ships with placeholder hair imagery so it looks finished out of
the box. Replace these with photos from Tayler's portfolio
([@tayler_made_hair](https://www.instagram.com/tayler_made_hair/)) by
overwriting the files in `images/` with the same filenames:

| File              | Where it appears                          | Suggested crop      |
| ----------------- | ----------------------------------------- | ------------------- |
| `hero.jpg`        | Home hero portrait                        | Vertical, 4:5.4     |
| `portrait-01.jpg` | Home — "Dimensional color" signature card | Vertical, 4:5       |
| `portrait-02.jpg` | Home — "IBE rows" + portfolio tall tile   | Vertical, 4:5       |
| `portrait-03.jpg` | Home — portfolio wide tile                | Wide / 16:9         |
| `portrait-04.jpg` | Services — Base + Gloss                   | Vertical, 4:5       |
| `portrait-05.jpg` | Home — "K-tips" + Services K-tips         | Vertical, 4:5       |
| `portrait-06.jpg` | Home — portfolio + Services Cut           | Vertical, 4:5       |
| `portrait-07.jpg` | Home — portfolio + Services Express       | Vertical, 4:5       |
| `portrait-08.jpg` | Home — portfolio + Services IBE feature   | Vertical, 4:5       |

Tip: export from Instagram at the largest size, drag into a folder
named `images/` in this directory (overwriting the existing files), and
refresh the browser. No code changes needed.

If a photo is differently shaped than the suggested crop, the CSS will
still cover it gracefully (`object-fit: cover`) — but matching the crop
keeps the editorial feel.

## Edit the copy

Open `index.html` and `services.html` in any text editor. The copy is
plain English between the tags. Search for things like the email
address (`hello@taylermadehair.com`) and replace with Tayler's real one.

Spots worth a personal pass:

- `index.html` → "A note from the chair" — Tayler can rewrite this in
  her own voice.
- `services.html` → service descriptions — same.
- The pull-quote on the home page ("She doesn't just do hair…") — swap
  for a real client quote when ready.

## Pricing

Per the brief, prices are placeholders (`—`) except for the IBE row
install (`$1,600`). Update them inline in `services.html` — search for
`service__price` and edit the values. They sit in the right-hand
column of each service block.

## Deploy

The site is a folder of static files. Anywhere that hosts static sites
will work. Three painless options:

1. **Netlify** — drag this folder onto <https://app.netlify.com/drop>.
   Done. Connect a custom domain in their dashboard.
2. **Vercel** — `npx vercel` in this folder, follow prompts.
3. **GitHub Pages** — push to a repo, turn on Pages in repo settings.

For a custom domain (e.g. `taylermadehair.com`), point the domain's
DNS at whichever host you pick and follow their instructions.

## Booking

The "Reserve a chair" buttons currently open an email composer. To
swap in a real booking platform (Vagaro, StyleSeat, GlossGenius,
Squarespace Scheduling, etc.), search both HTML files for
`mailto:hello@taylermadehair.com` and replace with the booking URL.

## Design notes

- Display font: **Fraunces** (variable, optical-sized)
- Body font: **Geist**
- Palette: warm bone, espresso, sienna
- Animations honor `prefers-reduced-motion`
- Mobile responsive (≤980px stacks; ≤600px refines)
