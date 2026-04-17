# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.

<!-- clawx:begin -->
## ClawX Tool Notes

### uv (Python)

- `uv` is bundled with ClawX and on PATH. Do NOT use bare `python` or `pip`.
- Run scripts: `uv run python <script>` | Install packages: `uv pip install <package>`

### Browser

- `browser` tool provides full automation (scraping, form filling, testing) via an isolated managed browser.
- Flow: `action="start"` → `action="snapshot"` (see page + get element refs like `e12`) → `action="act"` (click/type using refs).
- Open new tabs: `action="open"` with `targetUrl`.
- To just open a URL for the user to view, use `shell:openExternal` instead.

### Obsidian Notes (空岚学习笔记)

- Vault: "Knowledge base"
- Python学习笔记位置: `Python学习/`
- 文件清单:
  - `Python学习/00-总览` - 学习总览和目标
  - `Python学习/01-课程进度` - 进度追踪表
  - `Python学习/02-错题本` - 错题记录
  - `Python学习/03-待办事项` - 待办列表
  - `Python学习/04-学习日记` - 每日记录
  - `Python学习/04-学习日记/YYYY-MM-DD` - 每日日记
  - `Python学习/05-知识卡片` - 核心概念速查
- 更新时机: 每次学习、错题、徽章获得后都要同步更新到Obsidian
<!-- clawx:end -->
