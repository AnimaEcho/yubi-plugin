# Yubi for Claude

Yubi is a small assistant that lives on your Mac and operates the app in front of you. This plugin lets Claude use her: Claude reads the window you are looking at, then clicks, types, scrolls, opens apps and pages, and merges PDFs in Finder.

Claude does the thinking on your own Claude plan. Yubi does the hands, on your Mac.

## What you need

1. A Mac on macOS 26 or later.
2. Yubi, free from [yubichan.ai](https://yubichan.ai). Open it once and grant Accessibility when she asks.

## Install

### Claude Code

```
/plugin marketplace add AnimaEcho/yubi-plugin
/plugin install yubi@yubi
```

### Codex

```
codex mcp add yubi -- /Applications/Yubi.app/Contents/MacOS/yubi-mcp
```

### Claude Desktop, Cursor and other MCP apps

Add a local MCP server with this command:

```json
{
  "mcpServers": {
    "yubi": { "command": "/Applications/Yubi.app/Contents/MacOS/yubi-mcp" }
  }
}
```

The first time an app connects, Yubi asks whether that app may use her, checked by the app's code signature. The answer lasts until Yubi quits, and you can take it back sooner in her Settings.

## What Claude can do through Yubi

| Tool | What it does |
|---|---|
| `read_screen` | Reads the window in front as a numbered outline of its controls |
| `click` | Presses a button, link, tab or menu item |
| `type_text` | Types into a field |
| `press_key` | Presses Return, Tab, Escape, the arrows and a few more |
| `scroll` | Scrolls the window or brings an element into view |
| `open_app` | Brings an app to the front, launching it if needed |
| `open_url` | Opens a web page in your default browser |
| `wait` | Waits for a page to load, then reads again |
| `merge_pdfs` | Merges the PDFs selected in Finder into one new file |

## You stay in charge

- Every click, every bit of typing, every Return, Enter, Space or Delete, and every web address waits for your own yes on Yubi's card, which shows exactly what will happen. Claude cannot say yes for you.
- If you have not let Yubi click for you, she points at the control and waits for you to click it yourself.
- Text with line breaks is never typed through Yubi, since a line break can send.
- What Yubi reads goes to the AI app you connected and its provider. It never passes through Yubi's server, and Yubi keeps only a note that a read happened, not the text.
- Yubi reads the accessibility text of the window, never a screenshot.
- Password managers are never read.
- Only Yubi's own signed connector can talk to her, the connector only talks to the real Yubi, and only apps you allowed, checked by their code signature, get through.
- Press Stop on her card and the AI app's session ends at once.

Privacy policy: [yubichan.ai/en/privacy](https://yubichan.ai/en/privacy/)

## License

The plugin files in this repository are MIT licensed. The Yubi app is a separate product of International Design LLC.
