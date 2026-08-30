# OpenDominion

Browser-based, single-device deck-building game inspired by the structure of classic Dominion-style deck builders.

## Current scope

- 2–4 players: one human plus 1–3 bots.
- Action → Buy → Cleanup turn structure.
- Starting decks, draw/discard reshuffling, treasure economy, victory scoring.
- Fixed 10-card Kingdom set plus Copper/Silver/Gold, Estate/Duchy/Province and Curse piles.
- Interactive implementations of Village, Smithy, Market, Militia, Moat, Remodel, Workshop, Festival, Laboratory and Mine.
- End game when Province empties or any three supply piles are empty.
- Responsive premium card-room UI adapted from the project's SKAT visual baseline.
- No networking yet; multiplayer is intentionally deferred.

## Run

Open `index.html` directly in a modern browser, or serve the folder with any static HTTP server.

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

## Design direction

The visual language keeps the dark emerald felt, walnut framing, ivory cards, serif display typography and restrained gold interaction states from the SKAT baseline, but restructures the table around a deck-builder economy: supply piles dominate the upper board, the play area sits below them, and the player's hand forms a physical fan at the bottom.

## Architecture

The current MVP deliberately stays dependency-free:

- `index.html` — shell
- `styles.css` — responsive visual system
- `game.js` — rules engine, UI rendering and bot AI

The game state is plain JavaScript data, so a future multiplayer transport can serialize authoritative state without rewriting the rules layer.

## Next steps

1. Seeded/random Kingdom selection and presets.
2. Stronger bot personalities and strategy evaluation.
3. Animation pass for dealing, gaining and cleanup.
4. Save/resume and settings.
5. Multiplayer transport and lobby layer.
6. Automated simulation tests and browser/device QA.

## Note

OpenDominion is an independent implementation and is not affiliated with or endorsed by the publishers or rights holders of Dominion.
