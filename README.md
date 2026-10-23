# Likelyread plugin for Claude

[Likelyread](https://likelyread.com) tells you which of your emails were opened. This repository holds its plugin for Claude: the address of Likelyread's MCP server and a skill that tells Claude how to read the results. [plugins/likelyread](plugins/likelyread) has the plugin, with what it does and the data it handles.

## Install

In Claude Code:

```
/plugin marketplace add Hugo-SEQUIER/likelyread-claude-plugin
/plugin install likelyread@likelyread
```

Then run `/mcp`, pick `likelyread` and sign in with Google.

Likelyread's server, Chrome extension and agent tools are at [Hugo-SEQUIER/likelyread](https://github.com/Hugo-SEQUIER/likelyread).

## License

MIT: see [LICENSE](LICENSE).
