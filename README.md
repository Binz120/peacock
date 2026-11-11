# Peacock

An Omarchy theme built from a three-colour card: peacock `#0B3337` for the
field, tobacco `#6B351C` for selection and pressed fills, parchment `#D4B78E`
for body text, and gold `#D8B379` for the lettering. Every other token is a
lift or drop of those four; hue only leaves them for the status and code slots,
at lightness that keeps text at or above 4.5:1 on the field.

![Peacock with a palette specimen and an editor open](preview.webp)

The gold-to-parchment gradient rides the focused window, the bar and the popups;
the selection is a warm tobacco so parchment text stays readable at 8.6:1.

| Anchor | Hex | Role |
|---|---|---|
| Peacock | `#0B3337` | windows, panels, terminal paper |
| Tobacco | `#6B351C` | selection, pressed fills |
| Parchment | `#D4B78E` | body text (8.6:1 on the field) |
| Gold | `#D8B379` | accent, active border, links (6.9:1) |

---

## Apply

```bash
omarchy theme install https://github.com/Binz120/peacock
```

`omarchy theme install` clones the repo and applies it. The repository name is
the theme slug, so it arrives as `peacock` and lists as Peacock. A repository
install drops `hyprland.lua` and the terminal configs; the palette, shell
surfaces, GTK sheet, btop theme and wallpapers all survive, and the workspace
geometry falls back to the generated defaults.

## Wallpapers

Four stills ship, the garden first on apply; cycle them with
`omarchy theme bg next`.

- `01-tokyo-garden.jpg` — [wallhaven oxqyxm](https://wallhaven.cc/w/oxqyxm), 3840×2160
- `02-cat-in-the-grass.jpg` — [wallhaven k7dz96](https://wallhaven.cc/w/k7dz96), 3840×2160
- `03-crop-duster-dusk.jpg` — [wallhaven 4gepx7](https://wallhaven.cc/w/4gepx7), 1920×1080
- `04-autumn-road.png` — [wallhaven vg8y95](https://wallhaven.cc/w/vg8y95), 1920×1080

Your own wallpapers live outside the theme, in `~/.config/omarchy/backgrounds/peacock/`.

## Files

- `colors.toml` — the palette every Omarchy consumer reads
- `shell.toml` — bar, popups, launcher, menu, lock, polkit, notifications
- `gtk.css` — GTK3, GTK4 and libadwaita, including the list/columnview rows a
  symbol-only sheet leaves on Adwaita
- `btop.theme`, `chromium.theme`, `icons.theme`
- `unlock.png` (800×188, transparent gold wordmark) and `preview-unlock.png`
  (1920×1080) — the boot-decryption design shown under Appearance → Unlock
- `backgrounds/` — the four stills above
- `preview.webp` — 1920×1080 desktop capture

## Notes

- Terminal and editor configs are not shipped: a repo install would strip them,
  and the generated ones follow `colors.toml` anyway. The work tree that
  produced this repository keeps them locally.
- GTK deviations are deliberate: row hover is a gold tint over the view rather
  than flat `lighter_background`, disabled buttons sit on the field colour, and
  tooltips use `darker_background`. Measured with `measure-gtk-theme.py`, every
  text/background pair clears 3:1 and body text clears 4.5:1.
- `pressed-color`, `selection-color`, `heading`, `icon-large` and the per-section
  `border-width` keys are read by the shell (`Style.qml`, `Color.qml`).
- Wallpapers are third-party photographs; see LICENSE for what the MIT grant
  covers.
