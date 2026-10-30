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
- `id`: a unique clue number, kept as text, such as "01".
- `clue`: the instruction that leads players to this clue's location.
- `code`: the answer found at this location. Use a unique word or phrase; case and extra spaces are ignored. Use `null` for a code not decided yet.
- `next`: the ID of the clue displayed after this code is entered. For example WISDOM belongs to 01 and displays the text of 02.
- `starter`: true for the clues you can hand out as starting cards (01, 04, 10).
- `location` and `answer`: reference notes from the table; these are not displayed on the game page.

All entries must form one circular route. Every valid unique code counts once, regardless of starting point. Duplicate entries do not count twice. The total is calculated from the JSON. Code/route changes reset saved progress; text-only changes keep it.

## Still to finish
- Codes for 06 (cocktail menu) and 07 (book) are `null`. Replace them with quoted codes. They do not accept "TBD" and still count towards the total, so completion is blocked until they are filled in.
- Clue 07 still contains [Title], [page] and [word].
- The plant-pot location/answer is provisional.
- The other codewords are proposed in the Vault except CANDLE and COSTA RICA.
- The final passphrase is unspecified. Replace the clearly marked `finalClue` placeholder with your text before the event.

## JSON tips
Keep double quotes around text, commas between entries, and no comma after the last entry. Write `\n` inside a text string for a new line; escape quotes inside text as `\"`. Do not add comments. Invalid JSON, duplicate codes or broken links show a loading error rather than silently using old clues.

## Test and hosting
Open [the website](https://casparriis.github.io/riccos-halloween/). Because it loads a separate JSON file, opening index.html directly from disk is no longer supported; use GitHub Pages or a local HTTP server.

**View final clue (testing)** previews the ending without changing progress; **Back to clues (testing)** returns. **Reset progress (testing)** clears progress after confirmation. Remove testing controls before the event if players should not preview the ending.

Progress stays in this browser's local storage. There are no accounts, database or analytics. All JSON contents, including reference notes and answers, are publicly readable as part of the static site.

GitHub Pages uses **Settings → Pages → Deploy from a branch → main → /(root)**.
[Official publishing instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
