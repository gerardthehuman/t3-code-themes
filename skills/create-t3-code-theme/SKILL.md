---
name: create-t3-code-theme
description: Create or refine custom T3 Code themes from a palette, brand guide, or visual reference. Use for light and dark theme files, palette mapping, contrast fixes, and theme review.
---

# Create T3 Code Themes

Use this skill to create, tune, compare, or diagnose a T3 Code theme. Preserve the source palette and keep the interface easy to read.

## Workflow

1. **Find the palette.** Use the source that the user provides. If it is a live brand guide, read it before choosing colors. Note its neutrals, accents, and semantic colors.
2. **Read the current format.** Read current T3 Code theme docs or source, or inspect a recent T3 Code export. Use current color role names and file fields.
3. **Map colors to roles.** Set large surfaces first. Then map text, borders, controls, and interaction states to their roles.
4. **Build both modes.** Set `appearance` and `colors` for the base mode. Add the other mode under `variants`. For example, use `appearance: "light"` with `variants.dark`.
5. **Save the file.** Save project deliverables in `themes/`. Save installed themes in `~/.t3/userdata/themes/` when the user requests installation or publication.
6. **Inspect the theme.** Open Settings → Appearance. Inspect light and dark modes. Compare them with T3 Code defaults. Review text, borders, icons, hover states, and selected states. Revise colors that look washed out, too tinted, too strong, or hard to distinguish.

## Theme File Shape

Current exported theme files use `version`, `id`, `name`, `appearance`, `colors`, and optional `variants`. A theme pair has one base appearance and a variant for the other appearance.

```json
{
  "version": 1,
  "id": "example-theme",
  "name": "Example Theme",
  "appearance": "light",
  "colors": {
    "canvas": "#FCFCFC",
    "accent": "#267A45"
  },
  "variants": {
    "dark": {
      "canvas": "#171A18",
      "accent": "#69D58B"
    }
  }
}
```

Use the complete current `THEME_COLOR_ROLES` list when you build a full custom theme. Sparse color maps can inherit T3 Code defaults and create an uneven palette. Use valid CSS colors, such as six-digit hex values.

## Color Decisions

- **Keep broad surfaces neutral.** Use white, near-white, near-black, and low-chroma grays for the canvas, chrome, sidebar, code, and terminal surfaces. A brand color across every surface can make the interface look washed out or overly tinted.
- **Tint neutrals lightly.** Related themes can share the same neutral structure. Add a very slight source-color tint to separate family members, such as violet for Copilot or blue for Security.
- **Reserve strong colors for accents.** Use the source palette for focus, links, actions, and status colors. Compare text contrast on accent buttons. A dark accent with light text often works better in light mode. A light accent with dark text often works better in dark mode.
- **Balance borders and surfaces.** Keep `border`, `toolbarBorder`, and `sidebarBorder` visible without making every card and divider prominent. Keep input edges a little clearer than passive dividers when needed.
- **Keep interaction states distinct.** `toolbarControlHover` and `sidebarRowHover` control hover surfaces. `sidebarRowSelected` controls selected rows. `accentSurface` can affect selected icon backgrounds. These roles need enough contrast to show state, but their fills must not overpower the page.
- **Tune muted text for its background.** Compare `textMuted`, `mutedForeground`, `sidebarMutedForeground`, `placeholder`, and `iconMuted` with their actual surfaces. Pale palettes can make labels and icons too faint.

## Review Checklist

- The source palette is recognizable in both modes.
- Large surfaces stay neutral, with only a slight brand tint where useful.
- Primary text and muted text remain easy to read on their surfaces.
- Borders separate controls and panels without drawing too much attention.
- Hover and selected states are visible in both modes.
- The theme looks coherent in the running app, not only in its JSON file.
- The file is saved to the location the user requested.

