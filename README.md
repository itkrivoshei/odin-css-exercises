# Odin CSS Exercises

[![Static checks](https://img.shields.io/github/actions/workflow/status/itkrivoshei/odin-css-exercises/static-check.yml?branch=main&style=flat-square&label=static%20checks)](https://github.com/itkrivoshei/odin-css-exercises/actions/workflows/static-check.yml)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](LICENSE)

Static HTML and CSS exercises based on The Odin Project CSS curriculum.

## Tech stack

- HTML
- CSS
- GitHub Actions for lightweight static checks

## Scope

This repository contains small CSS practice exercises organized by topic:

- `foundations/` — selectors, cascade, grouping, chaining, and basic styling
- `margin-and-padding/` — spacing and box model exercises
- `flex/` — Flexbox layout exercises
- `grid/` — CSS Grid layout exercises
- `animation/` — simple transition and animation exercises

Some files come from the original course repository. Exercise implementations and cleanup changes are maintained in this fork.

## Run locally

No installation or build step is required.

Clone the repository:

```bash
git clone https://github.com/itkrivoshei/odin-css-exercises.git
cd odin-css-exercises
```

Open any exercise `index.html` file directly in a browser, or serve the repository locally:

```bash
python3 -m http.server 8000
```

Then open:

```txt
http://localhost:8000
```

## Verification

The repository includes a GitHub Actions workflow that checks:

- local stylesheet references in HTML files
- generated local files such as `.DS_Store`, `Thumbs.db`, and log files

Run the stylesheet reference check locally:

```bash
missing=0

while IFS= read -r html_file; do
  html_dir="$(dirname "$html_file")"

  while IFS= read -r href; do
    case "$href" in
      http://*|https://*|//*|"")
        continue
        ;;
    esac

    css_path="$html_dir/$href"

    if [ ! -f "$css_path" ]; then
      echo "Missing stylesheet: $css_path referenced by $html_file"
      missing=1
    fi
  done < <(grep -Eo 'href="[^"]+\.css"' "$html_file" | sed -E 's/^href="//; s/"$//')
done < <(find . -type f -name '*.html' | sort)

exit "$missing"
```

Check for generated local files:

```bash
find . \( -name ".DS_Store" -o -name "Thumbs.db" -o -name "*.log" \)
```

Expected output:

```txt
no output
```

## Project structure

```txt
.
├── animation/
├── flex/
├── foundations/
├── grid/
├── margin-and-padding/
├── .github/workflows/
├── .gitignore
├── LICENSE
└── README.md
```

## License

This repository is licensed under the [MIT License](LICENSE).

The original exercise material is from [The Odin Project CSS exercises](https://github.com/TheOdinProject/css-exercises), which is also distributed under the MIT License.
