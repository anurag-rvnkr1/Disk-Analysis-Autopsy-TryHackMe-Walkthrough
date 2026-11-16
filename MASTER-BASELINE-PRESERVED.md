# Master Baseline Files to Preserve

These shared files already exist in the destination repository. Their current content was inspected and matches the corresponding master design/configuration files, so the package intentionally leaves them untouched.

| Path in destination repository | Function |
|---|---|
| `_config.yml` | Root Jekyll configuration |
| `.github/workflows/pages.yml` | GitHub Pages deployment workflow |
| `docs/_config.yml` | Pages Jekyll configuration |
| `docs/_layouts/default.html` | Shared portfolio layout |
| `docs/assets/css/custom.css` | Compiled stylesheet baseline |
| `docs/assets/css/custom.scss` | Master source design system |

The root `_layouts/default.html` exists in the master repository, but the destination repository uses `docs/_layouts/default.html` for the configured `./docs` Pages source. Preserve the destination's current working Pages layout rather than adding another duplicate layout directory.

The destination's `.github/workflows/pages.yml` is already a valid Pages deployment workflow and should be retained. Do not replace it with the master's oddly named `.github/workflows ` directory (which contains a trailing space in the repository path).
