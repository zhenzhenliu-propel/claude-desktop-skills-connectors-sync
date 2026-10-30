# Claude Desktop skills and connectors: what carries into Claude Code

Notes on what a Claude Code session (Desktop app, Code tab) inherits from your claude.ai account, and what you still have to do by hand.

## Connectors: inherited from claude.ai

- Connectors that are connected and signed in on your claude.ai account are available in Code sessions.
- Connectors that exist on the account but are not signed in show up as unavailable. Sign them in under Settings → Connectors and their tools appear in Code too.
- Each session can switch connectors on or off separately, so one enabled in a chat is not automatically enabled in every Code session.

## Skills: inherited

- Your claude.ai skills are synced into `~/.claude/skills/synced/` by a session-start hook.
- Skills from installed plugins come through the plugins themselves.

## What is not shared

- **Local MCP servers.** Servers defined in the Desktop chat app's `claude_desktop_config.json` are not shared with Claude Code. Import them with:

  ```bash
  claude mcp add-from-claude-desktop
  ```

- **Plugin sign-ins.** MCP servers bundled with a plugin (for example Figma or Atlassian) are separate from your claude.ai connectors and need their own sign-in. Use `/mcp` in an interactive `claude` terminal.

## Summary

New connectors and skills added on claude.ai show up in Code automatically. The only manual steps are signing in to connectors and importing any local MCP servers you add later.
