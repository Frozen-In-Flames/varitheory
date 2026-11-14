# VariTheory V16

Gamified music theory lab + offline score compiler. Pure HTML/CSS/JS: no dependencies, no build step, no network calls.

**Live demo:** https://frozen-in-flames.github.io/varitheory/

Run it by opening the live demo, or download `index.html` and open it in any browser. It works fully offline.

## What it does

VariTheory teaches music theory by letting you build with it. Six lessons plus a library:

1. **Rhythm & Grid** — step sequencer with 4/4, 3/4, 5/4 and 7/8 meters, BPM control, and the Syncopation Pocket Challenge mini-game. The grid also feeds the drum stem in Lesson 5.
2. **Pitch & Scales** — all 12 roots, six scale systems (Ionian, Aeolian, Harmonic Minor, Melodic Minor, Dorian, Phrygian Dominant) built from interval formulas, degree names and frequencies, and the Functional Degree Hunter mini-game.
3. **Harmony & Cadences** — chord library (triads and seventh chords) with inversions, an 8-shape cadence bank with finality ratings, the Nashville Number System in every key, and the Blind Cadence Detective mini-game.
4. **Expression & Form** — envelope sculptor (waveform, lowpass cutoff, attack) and three form templates: Radio Verse-Chorus-Bridge (36 bars), Standard 12-Bar Blues, and Cinematic Ternary (24 bars).
5. **Score & Piano Roll** — a deterministic score compiler. Arrange and compose from your lesson settings, mutate the lead with a scale-locked variation engine, edit notes directly in the piano roll with undo/redo, and export Standard MIDI File (drums on channel 10) or 16-bit stereo WAV rendered offline.
6. **Rig, Mixer & FX** — nine virtual instrument presets ported from the v14 rig, a per-stem mixer (volume, pan, mute, solo), an insert FX rack with style presets, and a bring-your-own-sample instrument loader.
7. **Library & Log** — the complete music theory reference text, a persistent notes pad, and the full engineering change log from v0 to V16.

Progress, settings, grid, mixer, FX, score and notes autosave in the browser. Save/Load project in the header gives you a portable JSON backup. A loaded sample is not stored in the project file.

## Composition model

The primary compile path is 100% deterministic: the score is the exact mathematical result of the root, scale, tempo, meter and cadence cycle you dialed in. Mutation is a separate, optional action that varies only the lead, and every mutated note stays inside the active scale.

## Verification

V16 is the build that was exercised end to end in the Claude.ai demo environment across keys, scales, meters and modes, and re-verified mechanically after the version bump: data parity against the v14 source data, deterministic MIDI output (byte-identical across repeated compiles), mutation invariants over repeated runs, form-template note counts, drum-stem counts, and MIDI file structure (format 1, 480 PPQ).

## Lineage

VariTheory began as Theory Engine Studio, a React/TypeScript Space (v0 to v14) with a score-conditioned AI cover engine. V15 ported the exact v14 theory data into a zero-dependency single-file app and replaced the third-party AI cover with offline style presets. V16 is the publication release: the same verified engine, shipped as a public repository with GitHub Pages. The full history is in the app's Library & Log tab.

## License

Apache License 2.0. See [LICENSE](LICENSE).

Copyright 2026 Aries Hilton / Frozen In Flames.
