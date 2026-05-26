<div align="center">

# CSS Layout Collection

Static HTML and CSS layouts covering selectors, spacing, Flexbox, Grid, and simple animation states.

[![Static checks](https://img.shields.io/github/actions/workflow/status/itkrivoshei/odin-css-exercises/static-check.yml?branch=main&style=for-the-badge&label=static%20checks&logo=githubactions&logoColor=white)](https://github.com/itkrivoshei/odin-css-exercises/actions/workflows/static-check.yml)
[![HTML](https://img.shields.io/badge/HTML-static-e34f26?style=for-the-badge&logo=html5&logoColor=white)](foundations)
[![CSS](https://img.shields.io/badge/CSS-layouts-1572b6?style=for-the-badge&logo=css3&logoColor=white)](flex)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)

</div>

## Catalog

| Folder | Focus | Count |
| --- | --- | --- |
| `foundations/` | Selectors, cascade, grouping, chaining, descendant combinators | 6 |
| `margin-and-padding/` | Box model and spacing | 2 |
| `flex/` | Centering, headers, modal, page layouts | 7 |
| `grid/` | Grid page compositions | 3 |
| `animation/` | Hover and pop-up transitions | 2 |

Each entry includes source HTML/CSS, expected visual assets, and a solution folder for comparison.

## Run

No package install or build step is required.

```bash
git clone https://github.com/itkrivoshei/odin-css-exercises.git
cd odin-css-exercises
python3 -m http.server 8000
```

Open `http://localhost:8000` and browse to any folder, or open an `index.html` file directly.

## Static Checks

The workflow validates local stylesheet references and rejects generated local files such as `.DS_Store`, `Thumbs.db`, and log files.

Run a quick local generated-file check:

```bash
find . \( -name ".DS_Store" -o -name "Thumbs.db" -o -name "*.log" \)
```

Expected output: no files.

## Layout

```text
animation/
flex/
foundations/
grid/
margin-and-padding/
.github/workflows/static-check.yml
```

## License

[MIT](LICENSE)
