# The Masters 2026 — Draft Pool

A live, real-time Masters draft pool app. Single-file HTML + Firebase Realtime Database. No build step.

## Live URLs (GitHub Pages)

- **Player link (share with everyone):** https://jackhard1ng.github.io/masters-pool/
- **Admin link (keep private):** https://jackhard1ng.github.io/masters-pool/?admin=masters2026

> The admin link unlocks the score-entry console. Anyone with this URL can edit scores, so don't share it in the group chat.

## How it works

- First player to join becomes the **commissioner** and can start the draft once everyone clicks Ready.
- 6 golfers per team, 30 seconds per pick, snake order, randomized after a 15-second countdown.
- Auto-pick from the best available tier if a player times out.
- Leaderboard scores **best 4 of 6** (the worst 2 drop). Missed-cut golfers score +20.
- Admins can enter scores by total or hole-by-hole; updates push live to every connected client.

## Setup

1. Enable **GitHub Pages** for this repo (Settings → Pages → Source: `main` branch, `/` root).
2. In the Firebase console, make sure the Realtime Database rules allow read/write while the pool is running:
   ```json
   {
     "rules": {
       ".read": true,
       ".write": true
     }
   }
   ```
3. Open the player link above. First arrival = commissioner.
