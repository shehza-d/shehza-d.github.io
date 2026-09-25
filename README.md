# Shehzad Iqbal — Markdown portfolio

A minimal Jekyll portfolio modeled on the visual structure of Sierra Wang's academic website. Most content is ordinary Markdown, so regular updates do not require editing HTML or CSS.

## Where to edit

| Change | File |
|---|---|
| Biography, projects, experience, teaching, skills, achievements | `index.md` |
| Name, role, location, profile image, social links, navigation | `_config.yml` |
| Page structure and header icons | `_layouts/default.html` |
| Typography, spacing, colors, and mobile layout | `assets/css/style.css` |

After changing `_config.yml`, restart the local Jekyll server because configuration changes are not always reloaded automatically.

## Markdown examples

### Add a section

Add a level-two heading anywhere in `index.md`:

```md
## Talks

A short introduction to the section.
```

The heading receives an automatic anchor. For example, `## Talks` becomes `#talks` and can be added to the `navigation` list in `_config.yml`.

### Add a project

```md
### [Project name](https://github.com/username/project)

*React · TypeScript · Education*

A concise explanation of the project. You can place a [live demo](https://example.com) or any other link directly inside the text.
```

### Add an achievement

```md
- **Achievement name** — A short, verifiable explanation with an optional [source](https://example.com).
```

### Add lists and nested lists

Indent nested items by two spaces:

```md
- Main item
  - Nested item
  - Another nested item with a [link](https://example.com)
- Second main item
```

### Add an image

Put the image in `assets/images/`, then add:

```md
![Useful alternative text]({{ '/assets/images/example.jpg' | relative_url }})
```

Always include meaningful alternative text. The `relative_url` filter keeps the image working when the site is hosted in a GitHub project repository.

### Add a simple icon

For icons inside Markdown, the simplest option is a Unicode symbol or emoji:

```md
- 🏆 **Award** — Description
- 🔗 [Resource](https://example.com)
```

Header icons are inline SVGs in `_layouts/default.html`, which avoids an icon-library dependency.

## Profile image

The header currently uses the public GitHub profile image configured in `_config.yml`:

```yml
profile:
  image: "https://github.com/shehza-d.png?size=600"
```

To use a local image, save it as `assets/images/profile.jpg` and change the value to:

```yml
image: "/assets/images/profile.jpg"
```

## Local development

Install Ruby and Bundler, then run:

```bash
bundle install
bundle exec jekyll serve --baseurl ""
```

Open `http://localhost:4000`.

## GitHub Pages deployment

The workflow at `.github/workflows/deploy.yml` builds and deploys the Jekyll site after every push to `main`.

1. Push this project to the `shehza-d/shehza-d.github.io` repository.
2. Open **Settings → Pages** in that repository.
3. Set **Source** to **GitHub Actions**.
4. Push a change to `main` or run the workflow manually from the **Actions** tab.

The configured address is `https://shehza-d.github.io/`. Because this is a root user-site repository, `baseurl` must remain empty. If a custom domain is added, update `url` and add the domain to `CNAME`.

## Typography note

The reference site uses Open Sans. This portfolio uses Ubuntu as requested while preserving the reference site's font sizes, line heights, width, spacing, colors, and responsive behavior.
