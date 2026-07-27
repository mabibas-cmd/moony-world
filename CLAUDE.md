# Moony's World — Baby Website

A single-page trilingual (EN / PT / IT) baby website for Marina & Ryan (Melbourne) to share with family in Brazil, Italy & Adelaide, celebrating the arrival of baby "Moony". Live at https://mabibas-cmd.github.io/moony-world/ (GitHub Pages).

## What it is
- Cream (#FBF3E3), playful handmade-nursery aesthetic: ceramic "Moony's World" header image, Bricolage Grotesque display font, Nunito body, Gochi Hand accents.
- Hand-crafted ceramic digit/icon image assets under `assets/`.
- Tabs: **Countdown** (days-to-go with ceramic digits, pregnancy week + fruit size, weekly photo gallery with lightbox), **Wishlist**, **Baby Pool** (bolão), **Library**, **Wishes**.

## Data (Firebase Realtime Database)
All visitor submissions sync live for everyone via Firebase RTDB
(`moonys-world`, asia-southeast1). Paths:
- `wishlist` — registry items; builder is password-locked (edit access for Marina only)
- `pool_r1` — gender votes (one per name; re-voting with the same name updates it)
- `pool_r2` — birth-date / weight / length / first-word guesses
- `names` — name suggestions
- `books` — library book suggestions (covers from Google Books, Open Library fallback, ceramic covers as last resort)
- `wishes` — wishes wall notes (advice / wish)

The library and wishes seed their starter entries into the database on first
visit if the path is empty. Everything degrades to local-only (non-persistent)
if Firebase fails to load.

## Admin mode
Append `?admin` to the URL: shows the voter-by-voter gender breakdown and the
only delete buttons for votes, names, books, and wishes. Deletes are permanent
and global — never show delete buttons to regular visitors.

## Workflow
- Edit → drop `index.html` into `~/Desktop/MoonyWorld/` → `git add . && git commit && git push` → hard-refresh the live site (Cmd+Shift+R).

## Rules for Claude Code
- Keep this a single self-contained index.html unless we deliberately decide to split it.
- Preserve the design and aesthetic unless explicitly asked to change it.
- Make ONLY the change requested in each prompt; keep everything else exactly the same.
