# personal/ — your private data

This folder holds the personal info that gets injected into `index.html`
at page load: your name, email, affiliation, advisor, etc.

**AI assistants are forbidden from reading the files in this folder.**
See `CLAUDE.md` at the repo root for the rule.

## How to use

Edit `info.js` and replace every `<PLACEHOLDER>` value with the real
thing. Save, then reload the page in your browser. No build step.

The page falls back to the literal `<PLACEHOLDER>` text if you leave a
field unfilled, which makes it obvious what's still missing.

## What gets exposed publicly

Everything in `info.js` is shipped to the browser as a static asset
under `/personal/info.js`. Treat its contents as fully public:

- `email` is rendered as a clickable `mailto:` link on the homepage.
- `name_en`, `name_cn`, `role`, `affiliation`, `advisor` appear in the
  header.
- `page_title` is the `<title>` tag (visible in browser tabs and
  search snippets).

If a field should not be public, don't put it here.

## Editing without breaking AI workflows

If you ask an AI assistant to help you change the homepage, the
assistant will refuse to look in this folder. Paste the specific
value you want it to know directly into chat instead.
