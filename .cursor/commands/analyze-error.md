---
description: Analyze a build/test/runtime error and produce a fix plan
---

# Analyze Error

Use this command when `$ARGUMENTS` contains an error message, stack trace, or failing command output.

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
- Verification commands
- Regression risk

## Example Input

`TypeError: Cannot read property 'x' of undefined in packages/excalidraw/...`
