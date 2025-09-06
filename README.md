
# Wick-style Transcripts (GitHub Pages)

This package contains a Discord bot example and a static site ready to publish on GitHub Pages.

## How it works
1. The bot (in `/bot`) generates an HTML file per ticket into `/site/transcripts/<channelId>.html`.
2. You publish the `site/` folder to GitHub Pages (for example `<yourname>.github.io/<yourrepo>`).
3. The bot returns a public URL: `https://<yourname>.github.io/<yourrepo>/transcripts/<channelId>.html`.

## Deploy steps (quick)
- Edit `bot/.env.example` → copy to `bot/.env` and fill `TOKEN` and `GITHUB_PAGES_BASE` (example: https://youcefrr.github.io/my-transcripts/transcripts)
- `cd bot && npm install`
- Run the bot: `node index.js`
- When a ticket is closed, use the `/closeticket` command (or add your own command) to trigger the bot to write the HTML.
- Commit & push the generated file(s) from `/site/transcripts/` to your GitHub repo, then GitHub Pages will serve them.

## Automating push (optional)
- You can automate pushing new files using the GitHub REST API or `simple-git` and a machine/CI that has Git credentials.
- For automation, consider using a GitHub Action that watches a branch and deploys the `site/` folder to Pages.
