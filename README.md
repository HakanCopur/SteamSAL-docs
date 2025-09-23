
# SteamSAL MkDocs Theme Pack

Drop-in styling for **Material for MkDocs**.

## 1) Place files
Copy `docs/stylesheets/extra.css` into your repository.

## 2) Update `mkdocs.yml`
Add these fields (merge with your existing file):

```yaml
site_name: SteamSAL — UE5 Steam Achievements & Leaderboards
repo_url: https://github.com/your-username/SteamSAL

theme:
  name: material
  logo: assets/logo.png         # optional
  favicon: assets/logo.png      # optional
  features:
    - navigation.instant
    - navigation.sections
    - navigation.top
    - content.code.copy
    - toc.integrate
    - search.suggest
    - search.highlight
  palette:
    - scheme: default
      primary: indigo           # try: blue, cyan, deep purple
      accent: cyan
      toggle:
        icon: material/weather-night
        name: Switch to dark mode
    - scheme: slate
      primary: indigo
      accent: cyan
      toggle:
        icon: material/weather-sunny
        name: Switch to light mode

extra_css:
  - stylesheets/extra.css

markdown_extensions:
  - admonition
  - attr_list
  - tables
  - toc:
      permalink: true
  - footnotes

extra:
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/your-username
    - icon: fontawesome/brands/linkedin
      link: https://www.linkedin.com/in/your-profile/
```

## 3) Assets (optional)
Put your plugin icon at `docs/assets/logo.png` and reference it in `mkdocs.yml` as `logo` and `favicon`.

## 4) Serve locally
```bash
pip install mkdocs-material
mkdocs serve
```

This pack sets **Inter** for text and **JetBrains Mono** for code, adjusts heading sizes with `clamp()` for better scaling, improves code blocks and tables, and adds a utility `.center` class for images.
