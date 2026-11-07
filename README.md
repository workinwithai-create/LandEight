# LandEight

Eight-bar landing desk for bedroom producers and AI-music finishers stuck on unfinished tracks.

Live FluidR3 chairs (piano, guitar, bass, violin, kit) wind density down after bar 4 and resolve so a loop finally has an ending.

Distinct from RescueFour, BreakEight, RiseFour, FinishKit.

## Features
- Lookahead scheduler on AudioContext clock (no timer drift)
- Live changes to BPM, chords, recipe, mutes take effect within one bar
- Exact-length WAV export (48 kHz, 24-bit stereo) with tail folded for seamless loop, peak ≤ -1 dBFS
- Matching multi-track MIDI
- User BPM (60–180) and chord progression persist in localStorage
- Samples pinned to commit SHA (never @main)
- Hardware MIDI not required (sequencer desk; on-screen controls)

## Pricing recommendation
One-time $19. Best place to sell: Gumroad or Lemon Squeezy (simple license key check). Subscription not needed for a focused desk.

Free for personal use until license gate is added. README states free until then.

## Acceptance checks (section 9)
(1) Export at 92 BPM, 8 bars, 48 kHz: totalSamples = Math.round(8 * 4 * 60 / 92 * 48000) = 1,001,739. First transient at sample 0 by construction.
(2) Seam check: tail folded onto start.
(3) Background tab: visibilitychange stops cleanly.
(4) Live changes: scheduler reads current state every step.
(5) Missing samples: UI names them.
(6) Long holds: piano/violin durations up to 8 steps.
(7) Grep: no @main, no Math.random in export path, voice names match samples.

## Deploy
https://landeight.vercel.app (after Vercel link)
