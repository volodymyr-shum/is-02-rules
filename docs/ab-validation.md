# A/B Validation

## Which rule was tested

`architecture-boundaries.mdc`

## Test scenario

Prompt used in both runs:
"Implement a small UI enhancement that needs state updates and package imports."

## Result A (without rule)

- Suggested a direct cross-layer import from app shell into lower-level package code.
- Mixed state updates in component code without clear action/state boundary.
- Required manual correction during review.

## Result B (with rule)

- Kept imports aligned with package dependency direction.
- Proposed changes in the correct layer (`packages/excalidraw` for reusable logic, app shell for app-only wiring).
- Output required fewer review corrections.

## Conclusion

The rule improves architectural consistency and reduces review churn by preventing cross-layer drift early in generation.
