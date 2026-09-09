# Hi, I'm Darren Wang

Information Systems (Sistem Informasi) student at Binus University, Alam Sutera campus, Indonesia. I spend most of my time on coursework,
research papers, and building things that run unattended: trading-research pipelines, MCP servers,
Discord bots, and the odd Minecraft plugin.

The thing I care most about right now is **AI engineering**, specifically applying machine learning
to the Indonesian stock market (IDX) with honest evaluation: walk-forward validation, transaction
costs, and no lookahead. Most of that work lives in private repos while it is still research, but the
one public piece is below.

## Open source

**[stockbit-mcp](https://github.com/INo-xious/stockbit-mcp)** · co-maintainer ·
[![npm](https://img.shields.io/npm/v/stockbit-mcp?color=cb3837&logo=npm&label=npm)](https://www.npmjs.com/package/stockbit-mcp)

A Model Context Protocol server that puts the Indonesian stock market inside Claude, Cursor, or any
MCP client: broker flow (bandarmology), quotes, order book, fundamentals, screeners, alerts, and
chart drawing through your own Stockbit account. 138 tools in 17 families, on npm.

What I built there:

- The npm release pipeline. Publishes on a version bump to `main`, asks the registry (not git) whether a version exists, and publishes before tagging so a failed run leaves nothing stranded.
- The 7-day session fix. The CLI and the browser shared one token family, and every fresh process was silently revoking the other's session. Diagnosed by measuring token rotation, fixed with a shared encrypted access-token cache.
- The `analyze` and `analyze_screen` tools: a four-pillar verdict (broker flow, trend, valuation, patterns) with a confidence score that measures evidence quality, then run across a whole watchlist.
- Chartbit drawing (Fibonacci, zones), default-browser login, the live turnover sampler behind `/watch`, and the Claude Code skills for auth and status.

## Research projects (private while in progress)

**idx-ml** · Python, LightGBM, SQLite
Supervised signal model for IDX. Triple-barrier labels, point-in-time universe, append-only feature
store, walk-forward evaluation with purge, embargo, and a cost model. A paper book replays the
signals as an account. There is deliberately no order path anywhere in the repo. The finding so far
is the honest one: high win-rate strategies measured as the most money-losing, so the model
optimises expected value instead.

**IDX Analyst** · Python, Discord, Cloudflare Tunnel
A stock consultant (`/analyze BBCA` gives a BUY/HOLD/SELL note in plain language), a growth
screener over ~800 stocks, an IPO watcher, two paper-trading agents, and a live dashboard. Runs 24/7
on a Windows server under scheduled tasks and posts to Discord.

## Other things I have built

- **Atelier**: an encrypted notes-and-reminders dashboard, Cloudflare Pages front end + FastAPI back end, with a Tauri v2 desktop build.

## Stack

`Python` `TypeScript` `SQL` `PowerShell` ·
`pandas` `LightGBM` `scikit-learn` `Node.js` `FastAPI` ·
`Cloudflare` `GitHub Actions` `Docker` `Tauri` `MCP` `Claude Code`

## Contact

GitHub is the best place to reach me. Packages I publish are under [npm/dwstockbit](https://www.npmjs.com/~dwstockbit).
