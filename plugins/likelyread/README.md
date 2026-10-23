# Likelyread

Likelyread tells you which of your emails were opened. A tracked email carries a 1x1 image (the pixel) at the end of its HTML part. When the recipient's mail app loads it, Likelyread records a hit and classifies it as an open, a view of your own, or an Apple Mail Privacy Protection prefetch.

This plugin connects Claude to your Likelyread account and adds a skill that tells Claude how to read the results and report them.

## What you can ask

- Which of the emails I sent this week were opened?
- Did anyone open my last email, and when?
- What is the open rate of each of my campaigns?
- At what hours do my emails get opened?
- Are SPF, DKIM and DMARC set up for my sending address?

In Claude on the web, desktop and mobile, the connection reads results: your tracked emails and their opens, the hits on one email, campaign open rates, statistics and sender health. It can also move an email to another campaign. It does not add tracking to emails Claude writes there: the Likelyread Chrome extension tracks the emails you send from Gmail.

In Claude Code, the connection also has the tools that add the pixel to the emails Claude sends and register them. Claude asks you before tracking a campaign, and tracks only recipients who agreed to it where the law requires consent, as in the EU.

Campaign analytics, statistics and sender health are not available on every Likelyread plan. When one of them is not on yours, Claude tells you.

## Set it up

1. Add the plugin. In Claude Code, run `/plugin marketplace add Hugo-SEQUIER/likelyread-claude-plugin`, then `/plugin install likelyread@likelyread`.
2. Connect Likelyread: on claude.ai and in the desktop app, from the plugin's Connectors tab; in Claude Code, with the `/mcp` command.
3. Sign in with Google, as on the Likelyread dashboard, and approve the connection on Likelyread's page.

## Data

- The plugin holds a skill and the address of Likelyread's MCP server, https://app.likelyread.com/mcp. It runs no code on your computer and contains no token.
- When Claude uses a Likelyread tool, the request goes to app.likelyread.com, run by Likelyread. The server answers with data from your Likelyread account: email subjects, recipient and sender addresses, campaign names, send and open times, and how each hit was classified. Claude uses these answers to reply to you. The tools never return the IP address or user agent of a hit.
- Sender health looks up the public DNS records (SPF, DKIM and DMARC) of your sending domain, from Likelyread's server.
- In Claude Code, registering an email sends its subject, recipients, sender, campaign and send time to your Likelyread account.
- The token Claude gets when you sign in works only for these tools. You can disconnect Claude at any time from the Account page of the Likelyread dashboard.

Likelyread's privacy policy, https://likelyread.com/privacy, says what it stores and for how long. The terms are at https://likelyread.com/terms.

## Support

Open an issue at https://github.com/Hugo-SEQUIER/likelyread/issues, or write to hello@likelyread.com. Report a vulnerability privately to hello@likelyread.com, never in a public issue.

## License

MIT: see [LICENSE](LICENSE).
