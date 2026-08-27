# Hot Tottie Capital Management — Eventic-style rebuild

A full rebuild in the Eventic template's style: minimal centered nav, a
full-bleed looping video hero, centered eyebrow/headline/subtext blocks,
pill buttons, and a matching full-bleed video closing CTA at the bottom.
All copy is exactly what you provided — only image files and their
captions are left for you to fill in.

```
index.html
css/style.css
images/
  hero-bg.mp4        ← your aerial night video, already slowed to 0.5x
  hero-poster.jpg     ← poster frame shown before the video loads
  (8 image slots you still need to add — see below)
```

## 1. Add your photos

Nine images are referenced but not included — you asked to leave these
blank so you can add and caption them yourself. Drop files with these
exact names into `images/` and they'll appear automatically:

| File | Section |
|---|---|
| `weekly-call.jpg` | Inside the community |
| `trade-idea.jpg` | Inside the community |
| `member-chat.jpg` | Inside the community |
| `risk-review.jpg` | Inside the community |
| `community-voice.jpg` | Inside the community |
| `platform-dashboard.jpg` | The Long/Short Terminal |
| `watchlist.jpg` | The Long/Short Terminal |
| `post-mortem.jpg` | The Long/Short Terminal |

Any image format works if you update the extension in `index.html` to match
(`.png`, `.webp`, etc.). Aim for roughly a 4:5 portrait crop — that's the
shape each card expects.

## 2. Add your own captions

Each photo card has an empty caption line:

```html
<p class="caption"></p>
```

Type your caption text directly between the tags, e.g.
`<p class="caption">Wednesday's call on the CVNA short.</p>`. It renders as
bold white text over the bottom of the photo.

## 3. The video

`hero-bg.mp4` (already slowed to 0.5x, 1080p, ~5.7MB) plays at both the top
of the page and in the closing "Apply to join" section, muted and looped —
same technique Eventic uses. `hero-poster.jpg` is the frame shown while the
video loads.

**License reminder:** confirm you have the rights to use this footage on a
public site before it goes live — I don't know its original source or license.

## 4. Push to GitHub / deploy

Same process as before:

```bash
git init
git add .
git commit -m "Rebuild in Eventic style"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

Cloudflare Pages settings are unchanged: Framework preset = None, Build
command = blank, Build output directory = `/`.

## Customizing

- **Colors/fonts/spacing:** all in `css/style.css` under `:root` at the top.
- **Nav links:** currently `Inside / Benefits / Community / Terminal`,
  anchored to each section's `id` — edit the `<nav class="nav-links">`
  block in `index.html` to change labels or add pages.
- **Video overlay darkness:** controlled by `.video-overlay`'s gradient in
  `style.css` — increase the opacity values there if text is hard to read
  once your own video/photos are in place.
