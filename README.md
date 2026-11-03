# Intratio MCP server

<a href="https://www.claudeai.directory/launches/intratio" target="_blank" rel="noopener"><img src="https://www.claudeai.directory/badge/intratio" alt="Intratio - Listed on Claude AI Directory" width="220" height="54" /></a>

Intratio's remote MCP server connects AI assistants (Claude, ChatGPT, Cursor and any MCP client) to a quantitative equity research platform: daily machine-learning forecasts for 4,000+ US stocks on five horizons (3 days to 3 months), market screening, company fundamentals, market intelligence, your watchlist and saved portfolios, and an institutional portfolio optimizer.

This repository holds documentation only. The server is hosted by Intratio; there is nothing to install.

- **Endpoint (Streamable HTTP):** `https://mcp.intratio.com/mcp`
- **Official MCP Registry:** `com.intratio/mcp`
- **Full guide:** https://www.intratio.com/api/docs/

## Connect

**Claude (claude.ai, Desktop, mobile) and ChatGPT:** add `https://mcp.intratio.com/mcp` as a custom connector and click Connect. You are sent to Intratio to log in and approve access (OAuth 2.1), so there is no key to copy.

**Claude Code** (with your API key from the Intratio account page):

```
claude mcp add --transport http intratio \
  https://mcp.intratio.com/mcp \
  --header "Authorization: Bearer <your API key>"
```

**Cursor and other clients:**

```json
{"mcpServers": {"intratio": {
  "url": "https://mcp.intratio.com/mcp",
  "headers": {"Authorization": "Bearer <your API key>"}}}}
```

## Try asking

1. "What is Intratio's 3-month outlook for NVDA, and how has it changed this month?"
2. "Screen for large-cap tech stocks with the strongest 1-month signals."
3. "Optimize AAPL, MSFT, JNJ, XOM and JPM for the best risk-adjusted return."
4. "Is re-optimizing my latest saved portfolio worth it after trading costs?"

## Tools (33)

Every tool declares whether it only reads data or changes something.

- **Platform:** `get_platform_overview`, `get_usage`, `search_documentation`
- **Companies and signals:** `resolve_ticker`, `list_companies`, `list_sectors`, `get_company`, `get_signal`, `get_signals`, `get_signal_history`, `screen_signals`, `get_market_context`, `get_factor_exposures`, `get_model_validation`
- **Market intelligence:** `get_market_intelligence`, `get_portfolio_intelligence`
- **Watchlist and screens:** `get_watchlist`, `update_watchlist`, `list_saved_screens`, `run_saved_screen`, `get_preferred_signals`
- **Portfolios:** `list_portfolios`, `get_portfolio`, `get_portfolio_performance`, `export_portfolio`, `estimate_margin`
- **Optimizer:** `optimize_portfolio`, `rebalance_portfolio`, `reoptimize_portfolio`, `get_optimization`, `list_optimizations`, `save_optimization`, `get_optimizer_settings`

Unit costs, plans and scopes per tool: https://www.intratio.com/api/docs/

## Plans

A free Intratio account includes 25 tool units a day on a sample basket of stocks. Paid plans unlock the full coverage; the optimizer tools need Pro or above. See https://www.intratio.com/en/pricing/

## Links

- Website: https://www.intratio.com
- Documentation: https://www.intratio.com/api/docs/
- Privacy policy: https://www.intratio.com/en/privacy-policy/
- Support: support@intratio.com

Quantitative research output, not investment advice. Signals and optimizations are model-generated statistics, not personal recommendations.
