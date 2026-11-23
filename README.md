# rgx

Expand ripgrep matches in the terminal and scroll through the file in a small window.

    rgx -i term [path]

All `rg` options are passed through.

Keys: ↑↓/jk select or scroll, Space expand/collapse, PgUp/PgDn, g/G, e = open in `$EDITOR`, q = quit.

Matches are highlighted like in rg. For syntax highlighting in the expanded window install Pygments (optional; without it the output is monochrome): `sudo dnf install python3-pygments`.

## Installation

Requires ripgrep and Python 3. Symlink the script into your PATH:

    ln -s /path/to/tools/rgx/rgx ~/.local/bin/rgx
