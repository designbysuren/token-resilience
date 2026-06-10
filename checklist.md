# Token Resilience Audit Checklist

Run your design system through this in under an hour. Check each item; every unchecked box is a silent failure waiting for a user with a slider.

## Surface and color
- [ ] No token hardcodes an overlay or surface opacity as a single value
- [ ] Every text/surface pair has been tested at BOTH iOS 27 slider extremes (ultra clear and fully tinted)
- [ ] Contrast requirements are stored as ratios in the system, not just baked into chosen hex values
- [ ] Dark mode pairs were re-tested at both transparency extremes (4 total states, not 2)

## Depth and elevation
- [ ] Elevation tokens are semantic levels, not literal shadow values
- [ ] Depth remains perceivable when shadows are invisible (translucent surfaces)

## Spacing and layout
- [ ] Spacing tokens carry a base scale (e.g. 8dp) rather than only absolute pixels
- [ ] Spacing adapts to at least: device class, density setting
- [ ] Layout is defined as named regions, not pixel positions (slot-ready)
- [ ] Breakpoints have a defined meaning (or replacement) for spatial/XR contexts

## Type
- [ ] Every type style declares its minimum backdrop treatment
- [ ] Dynamic type scaling has been tested against your smallest spacing tokens

## Motion and shape
- [ ] Motion tokens can express physics (stiffness/damping), not only duration+easing
- [ ] Shape tokens define allowed states if the platform morphs shapes

## Documentation (the part everyone skips)
- [ ] Every policy above is written down where a human can find it
- [ ] Every policy above is written down where an AI agent can find it (agent layer / system.md)
- [ ] The intent behind each policy is documented, not just the rule

## Score
- 0–5 unchecked: resilient, publish your approach
- 6–12 unchecked: at risk, prioritise surface/color items first
- 13+ unchecked: your system was designed for a rendering context that no longer exists
