---
description: Analyze a build/test/runtime error and produce a fix plan
---

# Analyze Error

Use this command when `$ARGUMENTS` contains an error message, stack trace, or failing command output.

Typical Excalidraw error categories:

- Canvas rendering
- Scene serialization/restore
- Element updates and bindings
- Collaboration sync (room/network/Firebase)

Typical triage paths:

- `packages/excalidraw/scene/`
- `packages/excalidraw/element/`
- `excalidraw-app/collab/`

## Instructions

1. Restate the failing symptom in one sentence.
2. Identify likely root cause with file/path evidence.
3. Propose minimal fix with exact files to change.
4. Provide verification commands and expected pass criteria.
5. Mention regression risks and quick follow-up checks.

## Expected Output Format

- Failing symptom
- Root cause
- Minimal fix
- Files to change
- Error category
- Verification commands
- Regression risk

## Example Input

Examples:

- `SVG export produces invalid markup for arrow elements`
- `Firebase room sync stops after reconnect in collaboration mode`
- `Performance degradation in render loop with large scenes`

Example output:

- Failing symptom: SVG export fails for specific arrow scenes.
- Root cause: unsanitized/invalid SVG attribute generated in export path.
- Minimal fix: guard and sanitize export attribute generation.
- Files to change: `packages/excalidraw/scene/`, `packages/excalidraw/element/`
- Error category: Scene serialization/restore
- Verification commands: run export flow + `yarn test:app --watch=false`
- Regression risk: medium for other export shapes; re-test text/image export.
