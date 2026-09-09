# SANCTUARY BAND — Diagnostics

A single page that reads a SANCTUARY BAND's built-in black box so a support
report can be produced without shipping the band anywhere.

**Live page:** https://circuitf0rge.github.io/sanctuary-diagnostics/

## What it does

The wearer connects the band by USB-C and presses one button. The page reads:

- the restart history, with the cause of each restart and, for a watchdog
  reset, the task that caused it;
- the last 30 nights: duration, snores detected, nudges delivered, apnea-suspect
  events, battery at start and end;
- the current settings and firmware version.

It then shows a plain-language summary and a report to copy back to support.
It highlights the three things that matter: unexpected restarts, nights that
ended on an empty battery, and nights where snoring was **detected** but no
nudge was **delivered**.

## It only reads

The page sends exactly five console commands — `version`, `battery`, `cfg`,
`bootlog`, `stats` — all read-only. It contains no firmware, cannot flash or
modify the band, and changes no setting. Nothing is uploaded anywhere: the
report stays in the browser until the wearer copies or downloads it.

## Requirements

Chrome or Edge on a desktop computer (Web Serial is not available in Safari,
Firefox, or on phones), served over HTTPS, with the band connected by USB-C.

## Firmware updates

Firmware updating is a separate, access-controlled page and is deliberately
not part of this repository.
