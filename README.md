# rgx

Expand ripgrep matches in the terminal and scroll through the file in a small window.

    rgx -i term [path]

All `rg` options are passed through.

Keys: ↑↓/jk select or scroll, Space expand/collapse, PgUp/PgDn, g/G, e = open in `$EDITOR`, q = quit.

Matches are highlighted like in rg. For syntax highlighting in the expanded window install Pygments (optional; without it the output is monochrome): `sudo dnf install python3-pygments`.

## Installation

Requires ripgrep and Python 3. Symlink the script into your PATH:

    ln -s /path/to/tools/rgx/rgx ~/.local/bin/rgx

## Configuration

Optional config file: `~/.config/rgx/config.json` (or `$XDG_CONFIG_HOME/rgx/config.json`). See `config.example.json`.

- `theme`: name of a theme file without `.json` (default `catppuccin-mocha`; bundled: `catppuccin-mocha`, `dracula`)
- `window_height`: height of the expanded file window (default 15)
- `colors`: overrides for single colors, as `"#rrggbb"`, a 256-color index (0-255) or `"default"`. Hex colors are mapped to the nearest 256-color.

Color keys: `path`, `line_number`, `separator`, `gutter`, `gutter_match`, `match_fg`, `match_bg`, and syntax roles `comment`, `keyword`, `function`, `class`, `decorator`, `builtin`, `tag`, `string`, `number`, `operator`, `heading`, `deleted`, `inserted`.

## Themes

Each theme is a JSON file with all color keys, see `themes/`. Add your own by copying one to `~/.config/rgx/themes/<name>.json` (user themes take precedence over bundled ones) and set `"theme": "<name>"` in the config.
