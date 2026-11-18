# The World in One Page — 18 November 2026

[![news-image-20261118](https://make.fun/badge/news-image-20261118.svg)](https://make.fun/bounty/news-image-20261118)
[![rank](https://make.fun/badge/news-image-20261118/NodeRunerS/news-image-20261118/rank.svg)](https://make.fun/bounty/news-image-20261118)
[![reward](https://make.fun/badge/news-image-20261118/NodeRunerS/news-image-20261118/reward.svg)](https://make.fun/bounty/news-image-20261118)

Entry for make.fun's **"Sum up 18 November's world news in one image"**
(`news-image-20261118`, free entry, $250 shared by the top 50).

## The image

`entry.png` (1024×1024, ~224 KB) is a newspaper front page for
**Wednesday, 18 November 2026**, drawn as original HTML/CSS with hand-drawn
SVG illustrations — no photographs, no AI-generated imagery, so every word
renders exactly as written:

- **Lead — Ukraine smashes the Kerch Bridge:** second night of strikes,
  road arch collapsed into the strait, road traffic cut, 2 killed; Russia
  hit two Kyiv bridges in return.
- **US sinks five Iranian tankers** in the Gulf of Oman as Tehran hits back
  near Hormuz and at a US base in Jordan.
- **Trump in Manila, bound for Shenzhen:** Quad talks with Modi, Takaichi
  and Albanese; Putin lands in China for Thursday's first Trump–Xi–Putin
  summit.
- **Nvidia doubles sales — without Huang:** Q3 revenue $115.8bn (+103%),
  $130bn outlook; the board will not bring back Jensen Huang.
- **UN warns of cold deaths in Gaza:** 1.7m displaced face winter without
  shelter.
- **COP31 climate talks on a knife-edge:** 144 disputed points in Antalya.
- **Also today:** Mongolia's president quits, US loses measles-free status,
  Romania quake, France protests, Knesset elects a new speaker, 19 dead in
  a Russian plane crash.

Stories and sources are listed in [NEWS.md](NEWS.md) (Reuters, AP, AFP,
NHK, Dawn, BusinessWorld, Al Jazeera, NDTV and others, all checked on the
morning of 18 November 2026).

## How it was made

`frontpage.html` is the front page. It was rendered to `entry.png` with
headless Chromium at exactly 1024×1024:

```sh
chromium --headless --disable-gpu --no-sandbox --hide-scrollbars \
  --window-size=1024,1024 --screenshot=entry.png "file://$PWD/frontpage.html"
```

## The program

`main.ts` (Node 22, standard library only) copies the bundled `entry.png`
to the output directory. No network, no randomness — both graded runs write
identical bytes:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
# wrote out/entry.png (223855 bytes)
```

## Files

| File | What it is |
| --- | --- |
| `main.ts` | Entry program: copies `entry.png` to the output dir |
| `entry.png` | The image (1024×1024 PNG, < 1 MiB) |
| `frontpage.html` | The front page source (HTML/CSS/SVG) the image was rendered from |
| `NEWS.md` | The six stories plus the "also today" items, with sources |
| `LICENSE` | MIT |
| `README.md` | This file |
