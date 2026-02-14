# Interactive Piano Roll Viewer (audio-synced playhead + sliding window)

## Problem
Current piano-roll output is a static PNG. It does not support playback tracking or interactive exploration.

## Goal
Build an interactive piano-roll visualization synchronized with exercise audio playback.

## MVP Scope
- Render note bars from generated JSON (`note`, `duration`, `cumulative_duration`).
- Add a moving playhead synchronized with audio current time.
- Add a sliding/scrolling time window during playback.
- Support play/pause/seek and keep visualization in sync.
- Show piano keyboard reference.

## Customization (Phase 2)
- Orientation toggle: horizontal or vertical roll.
- Keyboard placement options (for example bottom for vertical mode).
- Toggle note labels on bars and/or keyboard keys.
- Basic display settings (zoom/window size/color theme).

## Acceptance Criteria
- Visual timing aligns with audio within acceptable tolerance.
- Seek in audio updates playhead immediately.
- Works on desktop and mobile browser.
- Handles at least 4-8 measures without frame drops.
- Clear fallback behavior when JSON/audio is missing.

## Non-Goals (for this issue)
- Full notation engraving.
- Real-time MIDI input.
- Automated pedagogy/adaptation logic changes.

## Implementation Notes
- Start with a minimal browser prototype (Canvas or SVG).
- Keep it modular so it can later replace/extend static PNG flow.
- Include one sample JSON+audio pair for testing.
