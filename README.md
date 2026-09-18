# Wordlinks

A word-chain guessing game. The first and last words are given — guess the missing links.
Every neighboring pair forms a compound word or phrase (*hot dog*, *dog house*, *house party*).

Play: https://harshabadami.github.io/wordlinks/

## Contents

- `index.html` — the game (generated; open it or serve it statically)
- `tools/compounds.txt` — 622 hand-curated two-word compounds, the chain graph
- `tools/daily.txt` — 14 hand-picked daily chains, rotated by date
- `tools/build_chains.py` — builds the chain graph → `tools/chains.json`
- `tools/build_site.py` — assembles `index.html` from `tools/template.html`
- `tools/test_wl.cjs` — logic + data tests (`node tools/test_wl.cjs`)

## Rebuild

```sh
python3 tools/build_chains.py
python3 tools/build_site.py
node tools/test_wl.cjs
```

## Game rules

- Guess letters (each revealed letter costs 8 pts) or type the whole word (100 pts clean).
- 3 stars ≥ 85% of max score, 2 stars ≥ 60%.
- 4 levels (4- to 7-word chains), sequential unlock, progress saved on-device.
