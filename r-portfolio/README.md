# R Portfolio — Quarto Website

A personal portfolio site built with [Quarto](https://quarto.org), showcasing Shiny apps, analyses, and R scripts.

## Structure

```
r-portfolio/
├── _quarto.yml              # Site config, navbar, theme
├── custom.scss              # Custom SCSS (fonts, cards, hero)
├── index.qmd                # Home page with featured projects
├── projects.qmd             # Project listing page
├── about.qmd                # About / CV page
└── projects/
    ├── shiny-app-template.qmd   # Template: copy for each Shiny app
    └── analysis-template.qmd    # Template: copy for each analysis
```

## Setup

1. **Install Quarto** — https://quarto.org/docs/get-started/
2. **Install R packages** you need in your analysis `.qmd` files
3. **Preview** the site locally:
   ```bash
   quarto preview
   ```

## Adding a Project

**Shiny app:**
1. Copy `projects/shiny-app-template.qmd` → `projects/my-app.qmd`
2. Fill in the title, description, shinyapps.io URL, and code walkthrough
3. Add a card to `projects.qmd` and optionally `index.qmd`

**Analysis / QMD:**
1. Copy `projects/analysis-template.qmd` → `projects/my-analysis.qmd`
2. Fill in your actual analysis code — it renders when the site builds
3. Add a card to `projects.qmd`

**Existing R script:**
- Create a `.qmd` wrapper that uses `#| eval: false` code blocks to show the script
- Or convert it to a literate document with `source()` and narrative

## Customisation

- **Colours & fonts**: edit `custom.scss` — change `$primary` and the Google Fonts import
- **Your name**: update `_quarto.yml` → `website.title`
- **Nav links**: update `_quarto.yml` → `website.navbar`
- **Social links**: update GitHub/LinkedIn URLs in `_quarto.yml` and `about.qmd`

## Deployment

### Quarto Pub (easiest, free)
```bash
quarto publish quarto-pub
```

### GitHub Pages
```bash
quarto publish gh-pages
```

### Netlify
```bash
quarto publish netlify
```

All three are free. Quarto Pub is the simplest for a first deploy.

## Hosting Shiny Apps

Deploy apps to [shinyapps.io](https://www.shinyapps.io) (free tier: 5 apps, 25 active hours/month):

```r
# In R, with rsconnect installed:
rsconnect::deployApp("path/to/your/app")
```

Then embed the app URL in your `.qmd` using the `<iframe>` block shown in the template.
