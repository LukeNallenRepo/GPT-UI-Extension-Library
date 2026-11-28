---
author: "Luke Nallen"
---

# Practical UI Design and Build Recipe

## Before writing code
- Identify the one primary user task and the top three supporting tasks.
- Sketch the page hierarchy and navigation.
- List data inputs, permissions, empty/loading/error states and responsive constraints.
- Read the relevant app profile and inspect the current implementation.

## Layout recipe
- Use a stable application shell.
- Give the page a clear title, context and primary action.
- Group related content into sections.
- Use a responsive grid with consistent gaps.
- Put the most important content first.
- Keep secondary controls close to the content they affect.
- Avoid nested cards inside cards unless grouping truly requires it.

## Attractive dashboard recipe
- Use one strong page title and a compact supporting description.
- Present 3–5 high-value summary metrics, not a wall of KPIs.
- Give the main chart or work queue enough space to be useful.
- Use a bento grid only for distinct content priorities.
- Keep chart colours semantically consistent.
- Show freshness, source and date range.
- Use concise labels and aligned numbers.
- Provide useful empty states instead of blank rectangles.

## Glassmorphism recipe
- Apply translucent surfaces selectively to overlays, floating panels or featured elements.
- Keep the underlying text contrast strong.
- Add a subtle border to define the glass edge.
- Use blur sparingly; provide a solid surface fallback.
- Do not put every card on a translucent blurred layer.

## Responsive recipe
- Collapse sidebars before they become cramped.
- Stack cards and controls in a predictable reading order.
- Convert dense tables to mobile row cards or an intentional scroll container.
- Move secondary inspectors into drawers.
- Preserve primary actions and context.

## Final polish
- Align edges and baselines.
- Remove redundant labels and decorative separators.
- Make interactive states visible.
- Use consistent icon sizes.
- Check long titles, empty content, large numbers and narrow widths.
- Verify that the interface remains understandable without colour or animation.
