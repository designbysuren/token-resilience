# Example: Spacing token, before and after

## Before (fixed value — wrong on half your devices)

```json
{
  "spacing": {
    "lg": "24px"
  }
}
```

## After (adaptive policy — aligned with M3 Expressive spacing)

```json
{
  "spacing": {
    "lg": {
      "base": "24dp",
      "scale": "8dp",
      "adapts_to": ["device_class", "density"],
      "contexts": {
        "watch": "16dp",
        "desktop_comfortable": "32dp",
        "xr_spatial": "see layout regions"
      }
    }
  }
}
```

The 8dp scale is the constant. The resolved value is contextual. This matches how Material 3 Expressive now treats spacing: tokens applied to margins, padding, and gaps that adapt programmatically to device type and density.
