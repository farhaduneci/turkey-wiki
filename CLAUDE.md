# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

Documentation-only wiki about living in Turkey. All content is Markdown. No build system, no tests, no dependencies.

## Content Guidelines

- All information is personal experience + publicly available sources — not legal/financial/immigration advice (see DISCLAIMER.md)
- License is CC BY 4.0 — attribution required on derivative work
- Keep entries factual and verifiable; note when things change frequently (visa rules, prices, government procedures)
- FAQ.md and RESOURCES.md exist but are empty — fill before linking from other files

## Structure

Content is organized into topic directories at repo root. Each directory has its own `README.md` index that links to files within it. The root `README.md` links to each directory. New topic: create a directory, add content `.md` files, add a `README.md` index inside, link the directory from root README.

Current directories:
- `banking/` — `tax-number.md`, `bank-account.md`
- `mistakes/` — `document-translation.md`
- `transportation/` — `istanbul-airport.md`

## Privacy

First-person experience and observations are encouraged — they're what makes this useful. Avoid specific location data that could identify where someone lived or was heading (exact addresses, specific transit coordinates like exit numbers, floor numbers, platform numbers).

## Cross-linking

Files within a directory should link to related files using relative paths (e.g. `[Bank Account](bank-account.md)`).

## Contributing Conventions

- Open an issue for outdated/incorrect info
- PRs welcome for corrections and additions
- Flag time-sensitive information (prices, fees, procedures) with a note that it may change
