# Token Resilience

**An audit framework for design tokens in the era of user-controlled rendering.**

In June 2026, two things happened in the same month:

- Apple shipped a transparency slider in iOS 27 that lets every user adjust Liquid Glass from ultra clear to fully opaque. A core visual property of every surface is now user-controlled.
- Google's Material 3 Expressive introduced spacing tokens that programmatically adapt to device type and density, motion driven by physics tokens, and a layout scaffold spanning mobile, desktop, and XR.

Both point at the same conclusion: **a design token is no longer an answer. It is a policy.**

A token that stores a fixed value (`overlay.opacity: 0.72`) silently assumes a rendering context that no longer exists. A resilient token defines the range of acceptable outcomes and the constraints that must hold across that range.

This repo gives design system teams 3 things:

1. **The Token Resilience Matrix** (`matrix.md`) — every major token category scored against the new reality, with the specific failure mode and the policy rewrite.
2. **An audit checklist** (`checklist.md`) — run your own system through it in under an hour.
3. **Before/after examples** (`examples/`) — fixed tokens rewritten as policy tokens.

## Who this is for

Design system maintainers, design engineers, and anyone whose tokens are consumed by more than one platform, one density, or one rendering context. Which, as of June 2026, is everyone.

## The one-line test

For any token in your system, ask: **does this token still hold when the user moves the slider?**

If the answer is "what slider," start with `matrix.md`.

---

Built by [Surendar Selvaraj](https://www.linkedin.com/in/surendarselvaraj). Part of the DSI (Design System Intelligence) family alongside the [DSI: Slot](https://www.figma.com/community/plugin/1620292195033489246) and DSI: Design System Intelligence Figma plugins.

Companion article: *Apple and Google Just Turned Your Design Tokens Into Suggestions* (Design Systems Collective).
