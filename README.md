# Ricco's Halloween mystery — test site

Open `index.html` in a browser to try it. Everything is in this one file; no installation or server is required. Press **Reveal clue** or Enter after typing a code.

| Sample code | Placeholder response |
| --- | --- |
| RAVEN42 | Sample clue 1 — Placeholder: replace this with your own clue for RAVEN42. |
| MOON17 | Sample clue 2 — Placeholder: replace this with your own clue for MOON17. |
| SHADOW9 | Sample clue 3 — Placeholder: replace this with your own clue for SHADOW9. |

Codes ignore letter case and spaces at the beginning/end. Unknown codes show an error; empty input asks for a code.

## Edit the clues

Open `index.html` in a text editor and find `EDIT YOUR CLUES HERE`. Change the three placeholder messages in the `clues` object. Add more entries using the same format, with a comma between entries. Keep codes uppercase. Messages can span lines inside backticks; escape a literal backtick or `${` with a backslash. Save and reload the browser. Text is displayed as plain text, not HTML.

There are no accounts, cookies, progress tracking, database, analytics, external fonts or dependencies. All codes and messages are delivered to the browser and can be read in the page source: this is a simple clue reveal, not a way to keep clues secret from someone inspecting the file.

## Publish free with GitHub Pages

These steps were checked against official GitHub documentation on 30 October 2026. Uploading these files does not by itself enable GitHub Pages.

1. Sign in to GitHub. Use **+ → New repository**.
2. Name it `riccos-halloween`, select **Public** (needed for Pages on GitHub Free), enable **Add a README file**, and choose **Create repository**.
3. In the repository, select **Add file → Upload files**. Upload `index.html` directly to the repository's top level, not inside another folder. Choose **Commit changes** to save it on `main`. Uploading this README is optional.
4. Open the repository's **Settings → Pages**.
5. Under **Build and deployment**, set **Source** to **Deploy from a branch**. Choose **main** and **/(root)**, then **Save**.
6. Wait for deployment. Revisit **Settings → Pages** and use **Visit site** once available. The address will normally be `https://YOUR-USERNAME.github.io/riccos-halloween/`. Share the actual address shown by GitHub with players.
7. Test all three sample codes on your phone. Later, edit/upload `index.html` and commit to `main` to publish updated clues automatically. Allow deployment to finish and reload the page.

Official references:
- [Create a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Configure the publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)


