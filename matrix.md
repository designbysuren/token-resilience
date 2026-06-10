# The Token Resilience Matrix

Every token category, scored against user-controlled rendering (iOS 27 transparency slider) and context-adaptive systems (Material 3 Expressive).

**Ratings:**
- **BREAKS** — the category fails silently under the new reality
- **AT RISK** — holds in most cases, fails at the extremes
- **ADAPTS** — survives if restructured as a policy
- **RESILIENT** — already context-independent

| Token category | Rating | What changed in mid-2026 | Failure mode | Policy rewrite |
|---|---|---|---|---|
| Opacity / transparency | **BREAKS** | iOS 27 hands surface transparency to the user, from ultra clear to fully opaque | Any hardcoded overlay opacity now competes with a user setting it cannot see | Define opacity as a range with a contrast floor, deferring to system transparency |
| Color contrast pairs | **BREAKS** | Text/surface pairs assumed a fixed backdrop; backdrops are now variable | A pair that passes WCAG at "tinted" fails at "ultra clear" | Store minimum contrast ratios as the token; resolve colors at render time against both slider extremes |
| Elevation / shadow | **AT RISK** | Liquid Glass signals depth with edge darkening and specular highlights, not shadows over opaque layers | Shadow-based depth disappears on translucent surfaces | Make elevation semantic (level 0 to 5); let each platform material render the level its own way |
| Spacing | **ADAPTS** | M3 Expressive spacing tokens adapt to device type and density on an 8dp scale | Fixed pixel values produce wrong density on watch, desktop, XR | Store base value + scale + adaptation contexts, not a single number |
| Typography | **AT RISK** | Legibility now depends on backdrop diffusion the user controls; dynamic type already varies size | Type that is readable at default transparency becomes unreadable at ultra clear | Pair every type token with a minimum backdrop treatment requirement |
| Shape / radius | **ADAPTS** | M3 ships a 35-shape library with built-in shape morph motion | A static radius cannot describe a shape that animates between states | Define shape as a set of allowed states plus morph behaviour |
| Motion | **ADAPTS** | M3 motion is now physics powered by tokens, not fixed durations | Duration+easing tokens cannot express spring physics | Store physics parameters (stiffness, damping) instead of milliseconds |
| Layout / breakpoints | **ADAPTS** | Expressive layout scaffold spans mobile, desktop, spatial, XR | Width-based breakpoints have no meaning on spatial canvases | Define layout as content-driven regions (slots) with per-context arrangement rules |
| Iconography sizing | **RESILIENT** | Optical size scales already context-aware on both platforms | Minimal | Keep, but verify against density tokens |
| Z-index / stacking | **RESILIENT** | Stacking order is logical, not visual | Minimal | Keep |

## How to read your score

Count your categories:
- 2+ BREAKS → your system has silent failures shipping right now on iOS 27 betas
- Mostly AT RISK → schedule a token architecture review this quarter
- Mostly ADAPTS/RESILIENT → you are ahead; document the policies so AI agents can consume them too

## The deeper pattern

Each BREAKS rating shares one root cause: the token stores the **output** of a design decision instead of the **decision itself**. `0.72` is an output. "Maintain 4.5:1 contrast at any user transparency" is the decision. The platforms just made the outputs unstable. The decisions still hold.
