# Voice Prompt Input for Exercise Generation (MVP)

## Problem
HarmonyHub currently expects typed text prompts. This creates friction for users who prefer speaking, have motor constraints, or are in teaching contexts where voice interaction is faster than typing.

## Goal
Allow users to provide vocal instructions that are transcribed and used as input for the existing text-prompt generation flow.

## Scope (MVP)
- Capture voice input from microphone or uploaded audio.
- Run speech-to-text (STT) and produce a prompt transcript.
- Show transcript for user confirmation/edit before generation.
- Reuse current text-prompt pipeline after confirmation.
- Provide basic error handling for failed transcription or empty output.

## Acceptance Criteria
- User can generate an exercise from voice input without manually retyping.
- Transcript is visible and editable before submission.
- Works with at least one supported language/accent profile documented in the repo.
- Fails gracefully when STT confidence is low or audio quality is insufficient.
- Includes tests for transcript handoff into generation input.

## Non-goals (MVP)
- Real-time conversational assistant behavior.
- Talking-score output (that is a separate output-side feature).
- Full multi-language support.

## Privacy and Data Notes
- Document where audio is processed (local vs remote service).
- Avoid storing raw audio by default unless explicitly enabled.
- If remote STT is used, document provider and data handling assumptions.

## Implementation Notes
- Keep STT as a pluggable adapter so providers can be swapped.
- Keep this feature strictly input-side and separate from output audio narration features.
