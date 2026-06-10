# Example: Opacity token, before and after

## Before (fixed value — BREAKS under iOS 27)

```json
{
  "surface": {
    "overlay": {
      "opacity": 0.72
    }
  }
}
```

The decision this token was supposed to encode: "content behind an overlay should never compete with the overlay's text."

What it actually encodes: a number that was correct on one device, at one setting, in 2024.

## After (policy token — resilient)

```json
{
  "surface": {
    "overlay": {
      "opacity": {
        "range": [0.4, 1.0],
        "default": 0.72,
        "respects": "system.transparency",
        "constraints": {
          "min_text_contrast": "4.5:1",
          "fallback": "increase_opacity_until_constraint_met"
        }
      }
    }
  }
}
```

The decision is now in the token. Any renderer, human, or AI agent reading this knows what must stay true when the user moves the slider.
