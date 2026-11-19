# AERO — the clear-sky groovebox

AERO is a custom firmware for the M-VAVE FM-1 with a Frutiger Aero look: sky gradients, glossy glass cards, aqua
selection bars, green pill badges and bubbles. It is a fork of [NEON](https://github.com/LotionOnTheSkin/NEON)
(itself a fork of [Felucca](https://github.com/hugelton/Felucca)) and keeps NEON's synth engine as a sound source;
the AERO work is the look, the menus and the sounds. Everything else is Felucca as it is upstream.

- **Download:** [Releases › aero-latest › `aero.fwsc`](../../releases/tag/aero-latest), built by GitHub Actions on every push
  (`.github/workflows/build-aero.yml`).
- **Try it in the browser:** open the [FM-1 emulator](https://joakimeriksson.github.io/fm1-emu), load `aero.fwsc`, press Start.
- **The sounds:** every factory preset is AERO's own, made for the Frutiger Aero theme: glassy bells, water, air,
  drum breaks. Each engine's list (ENG on the PRESETS page) was replaced in place; NEON's synthwave presets are gone.
  - **AERO** (NEON's engine, renamed; last in the list; `firmware/src/eng_neon.c`, MIT): WAVE SUPER / PWM / SUB /
    GLASS. GLASS is a glassy FM tone (SPRD becomes RTIO, the bell's overtone ratio 1 + RTIO / 16; BLND becomes BRIT,
    the brightness, which mellows as the note fades). 16 presets: pads SKYGLASS, MEADOW, CLOUDS, AURORA, HALO PAD;
    bells AQUABELL, CRYSTAL, DEW BELL, ICE BELL, TIDE BELL; CLEAR KEYS; plucks DEW DROP, SPARKLE, RAINDROP, BUBBLES;
    SOFT SUB.
  - **Breaks:** DRUM's kits (BREAK KIT, CRISP BREAK, SPLASH KIT, DEEP SEA, BOOM BAP, RAIN PERC) and five break
    patterns in SAVE > PHRASES (14 SURF BRK, 15 BOOM BAP, 16 SPLASH, 17 DRIZZLE, 18 TIDAL), drum grids with several
    drums a step; each kit suggests one. SLICE cuts up the built-in break (SURF CHOP, DRIP STUTTER, TIDE ROLL,
    BACKWASH).
  - **Bells and water elsewhere:** PHYS (GLASS BELL, WIND CHIME, STEEL PAN, DRIP DRUM, SEA HARP ..), FM6 (GLASS EP,
    CELESTA, GLASS PAD ..; its patches retuned and renamed), NOISE (OCEAN, RAINFALL, BUBBLES, STREAM ..), and airy
    leads, pads and basses on ANALOG, PHASE, LOFI, VOICE, TRIO, WHEEL and GRAIN. SAMPLE keeps its recorded
    instruments (PIANO, FLUTE, SAX).
  - Felucca-Engines (MIT: ANALOG, PHASE, LOFI, TRIO, WHEEL, NOISE) is vendored in `firmware/engines/` (from upstream
    d026007) so these presets can live in it.
- **The look:** Frutiger Aero. A clear-sky boot screen (a glossy aqua sun, bubbles, a green hill), the AQUA palette
  (mist, deep aqua, ink, leaf green) as the default (MENU > COLOR still offers NEON's SUNSET and Felucca's palettes),
  Nunito for values and titles and Open Sans for labels. In AQUA (STYLE FLAT) the main pages are glass over a sky:
  frosted header and footer bars, translucent cards and panel with soft shadows, glossy aqua selection pills and
  green / red badges, bubbles in HOME's scope.
- **LAGOON:** tap HOME from CLOCK (HOME > MIXER > CLOCK > LAGOON). A clear-sky lagoon that plays along: each track
  sends up bubbles from its quarter of the floor, the sky and sun brighten with the mix, the water line rings out on
  the kick, seaweed sways to the beat, clouds drift, and a goldfish swims back and forth, darting on the kick. In the
  SUNSET palette the page shows NEON's SUNSET DRIVE instead.
- **Status:** experimental, work in progress. It passes Felucca's host test suite; it has not yet been played on a real
  FM-1.

Engine numbers: NEON is engine 15; 14 stays reserved for Felucca's ADPCM, so projects move between this firmware,
NEON and upstream Felucca without a mismatch. A project or user preset with a NEON sound does not load on upstream Felucca.

---

# Felucca

[![License: GPL-3.0-only](https://img.shields.io/badge/license-GPL--3.0--only-blue.svg)](LICENSE)

Felucca is open-source custom synthesizer firmware for the **M-VAVE FM-1**.

The FM-1 is the only supported hardware target. This project does not provide, maintain, or accept requests for ports to other devices or software platforms.

## Install

**Stable release: 1.8.1.** Connect your FM-1 by USB and use the [web installer](https://hugelton.github.io/Felucca/) in Chrome or Edge. The installer offers a way back to the official V15 firmware. Back up your projects and presets before changing firmware.

**Newer FM-1 flash: 1.8.2 beta.** Some newer FM-1 units use UC25HQ80 flash (JEDEC ID `0xB36014`). [1.8.2-beta](https://github.com/hugelton/Felucca/releases/tag/v1.8.2-beta) adds recognition for that chip; testing on the revised hardware is still pending. See [issue #320](https://github.com/hugelton/Felucca/issues/320). It is not the stable release.

## Project resources

- [Web installer](https://hugelton.github.io/Felucca/)
- [Web editor](https://hugelton.github.io/Felucca/webapp/editor/) ([source](https://github.com/hugelton/Felucca-WebApp))
- [Manual and release notes](https://github.com/hugelton/Felucca/wiki/Home)
- [Building from source](BUILDING.md)
- [Issue tracker](https://github.com/hugelton/Felucca/issues)

The firmware uses [Felucca-Engines](https://github.com/hugelton/Felucca-Engines) (MIT) for its built-in sound engines and [felucca-bsp](https://github.com/hugelton/felucca-bsp) (MPL-2.0) for the FM-1 hardware layer. Neither repository implies support for Felucca on other hardware.

## Development and support

Felucca focuses on the FM-1. Third-party modifications and ports are independent projects and are not tested or supported here. Contributions are considered at the maintainer's discretion; no development schedule or ongoing support is promised.

Felucca is developed with the assistance of AI coding agents (code, tests, documentation, translation, maintenance). Design, features, sounds and direction are the maintainer's or the community's; no generative AI is used for music, icons or artwork. See [On AI-Assisted Development and Responsibility](https://github.com/hugelton/Felucca/discussions/166).

## Credits and licence

Felucca is free software under [GPL-3.0-only](LICENSE); the Hügelton Sample Pack is CC0 1.0. The engines and hardware layer retain their own licences. See [CREDITS.md](CREDITS.md) and [LICENSING.md](LICENSING.md).

M-VAVE and FM-1 are trademarks of their respective owners. Felucca is not affiliated with, endorsed by or supported by M-VAVE.

Copyright (C) 2026 Leo Kuroshita (@kurogedelic), Hügelton Instruments
