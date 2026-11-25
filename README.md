# GojoxKaguya-reacts

Sticker pack for the GojoXkaguya bot's `.sreacts` sticker-flood mode.

Reply to any message with `.sreacts 20` and the bot sends 20 random stickers
from this pack, each quoting that message, then deletes the command message.
`.sreacts demon 5` sends the sticker named `demon` 5 times (max 30).

## How to add stickers

1. Upload your sticker files into the `stickers/` folder.
   - Format: **.webp only** (WhatsApp sticker format).
   - Keep each file small (a few hundred KB at most) so the bot can fetch
     and send it quickly.
2. Add one entry per sticker to `stickers.json`:
   ```json
   [
     { "name": "demon", "file": "demon.webp" },
     { "name": "lion", "file": "lion.webp" }
   ]
   ```
   - `name`: lowercase, no spaces — this is what users type
     (`.sreacts demon 5`).
   - `file`: the exact filename inside `stickers/`.
3. Commit + push. The bot reads `stickers.json` fresh every 10 minutes
   (in-memory cache), so new stickers show up on their own — no bot
   restart, no database, nothing else to update.

## Removing a sticker

Delete the file from `stickers/` and remove its entry from `stickers.json`.

## Files

| File | What it is |
|---|---|
| `stickers.json` | The manifest — the bot reads this to know which stickers exist. |
| `stickers/` | The `.webp` sticker files. |
