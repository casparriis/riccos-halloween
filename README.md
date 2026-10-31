# Ricco's mystery — editing guide

## Edit clues and codes
The website's single source is [clues.json](clues.json). There are no clue texts or codes in index.html.

1. Open [clues.json on GitHub](https://github.com/casparriis/riccos-halloween/blob/main/clues.json).
2. Click the pencil (Edit this file).
3. Change the text inside quotes for `clue`, `code` or `finalClue`.
4. Click **Commit changes** and save to **main**.
5. Wait for GitHub Pages to update, then reload the website.

The Vault table was imported from [Halloween party 2026 — Mystery treasure hunt](https://drive.google.com/file/d/1izvENFt8eHRpfla2ZNx-1xTj_0wB3LP1/view). That note remains unchanged as the source reference. Future website edits belong in this JSON; editing the Vault does not automatically update the site. No separate editable Drive copy is used.

## What each field means
- `gameVersion`: change this to reset everyone's saved progress for a new game.
- `finalClue`: the full-page clue revealed when all unique codes are found.
- `finalAnswerPrompt`, `acceptedAnswers` and `successMessage`: the answer field label, accepted identities, and completion text.
- `notificationEmail`: the approved public recipient address for correct-answer notifications. FormSubmit requires activation from its email before delivery works. Wrong answers do not send a notification; the same browser remembers a successful notification until progress is reset.
- `id`: a unique clue number, kept as text, such as "01".
- `clue`: the instruction that leads players to this clue's location.
- `code`: the answer found at this location. Use a unique word or phrase; case and extra spaces are ignored. Use `null` for a code not decided yet.
- `next`: the ID of the clue displayed after this code is entered. For example WISDOM belongs to 01 and displays the text of 02.
- `starter`: true for the clues you can hand out as starting cards (01, 04, 10).
- `location` and `answer`: reference notes from the table; these are not displayed on the game page.

All entries must form one circular route. Every valid unique code counts once, regardless of starting point. Duplicate entries do not count twice. The total is calculated from the JSON. Code/route changes reset saved progress; text-only changes keep it.

## JSON tips
Keep double quotes around text, commas between entries, and no comma after the last entry. Write `\n` inside a text string for a new line; escape quotes inside text as `\"`. Do not add comments. Invalid JSON, duplicate codes or broken links show a loading error rather than silently using old clues.

## Hosting and progress
Open [the website](https://casparriis.github.io/riccos-halloween/). Because it loads a separate JSON file, opening index.html directly from disk is no longer supported; use GitHub Pages or a local HTTP server.

The final clue unlocks only after all unique codes have been found. Testing and preview controls have been removed.

A small **Reset progress** button is available at the bottom once a player has found a clue, including on the final screen. It asks for confirmation before clearing this device’s found clues and saved notification state. Cancelling changes nothing. Reloading normally restores progress and is the first thing to try if a page is stuck.

Progress stays in this browser's local storage. There are no accounts, database or analytics. All JSON contents, including reference notes and answers, are publicly readable as part of the static site.

GitHub Pages uses **Settings → Pages → Deploy from a branch → main → /(root)**.
[Official publishing instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
