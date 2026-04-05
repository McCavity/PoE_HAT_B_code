# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Sample/driver code for the **Waveshare PoE HAT (B)** — a Power-over-Ethernet HAT for Raspberry Pi
that includes an **SSD1306 OLED display** and fan control. The code is vendor-supplied by Waveshare
and was forked here for reference/customisation.

**Hardware**: Raspberry Pi 3B+ or Jetson Nano with the Waveshare PoE HAT B attached.

## Structure

```
PoE_HAT_B_code/
  python/
    examples/main.py              — demo script (display text/shapes on SSD1306)
    lib/waveshare_POE_HAT_B/
      POE_HAT_B.py                — fan control via I2C
      SSD1306.py                  — OLED display driver (128×32)
      *.ttf                       — bundled fonts
  c/
    examples/main.c               — C demo
    lib/                          — C library sources
```

## Setup (Python)

```bash
sudo apt-get install python3-pip python3-pil
sudo pip3 install RPi.GPIO smbus
sudo python3 PoE_HAT_B_code/python/examples/main.py
```

## Notes

- This is archived/reference code — no active development since 2023
- The original vendor source is from Waveshare; local changes (if any) are minimal

## Organisation Context

This repository is part of Henning Halfpap's personal GitHub collection, located at
`/Users/hhalfpap/git/projects/own` on the development machine.

- **Org index**: `/Users/hhalfpap/git/projects/own/org-index.json` — machine-readable
  metadata for all repos (last commit, CLAUDE.md presence, file count, etc.)
- **Org instructions**: `/Users/hhalfpap/git/projects/own/CLAUDE.md` — guidance for
  cross-repo maintenance tasks (checking sync status, stale repos, etc.)

For project-specific work, operate within this directory. For questions spanning
multiple repos, consult the org index first.

**Tooling rule**: Skills, plugins, and MCP servers are always installed at project level
(`.claude/settings.json` in this directory), never at user/global level.
