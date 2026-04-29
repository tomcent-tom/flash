# Flash – Requirements

## Functional

- Display flashcards with a flip animation (tap/click to reveal answer)
- **Two-level mastery per card:**
  - Level 1: Spanish → English
  - Level 2: English → Spanish
  - Passing level 1 promotes the card to level 2 (reinserted randomly)
  - Passing level 2 removes the card as fully mastered
- **"Again"** reinserts the card at a random later position at the same level
- **Home screen** shown on launch for session configuration before studying begins
  - Select theme (category): All, Pregnancy, Hospital, Parenting
  - Select cards per session: 5, 10, 15, 20, or All due cards
  - Shows how many cards are due today for the selected theme
  - Start button disabled when no cards are due
- Session deck is drawn randomly from due cards, capped to the selected card count
- Navigate back to home from the study screen (← Home button) or done screen (← Back to home)
- Navigate manually with prev/next and shuffle buttons
- Track score (got it / again counts)
- Progress bar showing mastered cards out of total
- Show level indicator per card (Level 1 · ES→EN / Level 2 · EN→ES)
- End screen when all cards are mastered, with score summary and restart
- Display a small version number at the bottom of the UI
- **Spaced repetition (SM-2):** card review intervals are scheduled using the SM-2 algorithm stored in `localStorage`
  - "Got it" at level 2 records a success and schedules the card for future review (interval grows with consecutive successes)
  - Cards not yet mastered in a session remain due and reappear in the next session
  - Session deck contains only cards due today (next review date ≤ today) plus any never-seen cards
  - "All caught up!" screen shown when no cards are due for review
  - End screen shows when the next batch of cards is due
  - "Reset progress" button clears all SRS history from `localStorage`

## Non-functional

- Static site — no backend, no build step
- Deployable to Vercel with zero config
- Mobile-first, works in a phone browser
- Installable as a PWA (manifest.json + iOS/Android meta tags) — add to homescreen works on both platforms
- Respects the system light/dark mode setting (`prefers-color-scheme`) — dark by default, switches to a light palette automatically when iOS/Android/desktop is set to light mode
