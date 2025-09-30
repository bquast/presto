# Presto

Presto turns Markdown repositories into clean static sites with zero configuration. Point it at a Git repository (or run it locally) and it will automatically pick the best Markdown entry point, render it to HTML, and wire up optional extras like Google Analytics and visual themes.

## Features

- **Zero configuration:** run `presto` in a repo or pass `user/project` (GitHub/GitLab) to build pages.
- **Smart Markdown selection:** if there is only one Markdown file Presto uses it, otherwise it prefers `README`, `index`, `main`, `landing`, or `home` files automatically.
- **Multi-page output:** every Markdown file in the project root becomes a page, with navigation links between them.
- **Theme store support:** point at `--theme` (and optional `--palette`) to pull CSS/HTML templates from the Presto theme store or local files.
- **Analytics ready:** supply `--ga <MEASUREMENT_ID>` to embed Google Analytics.
- **Cloudflare Pages friendly:** emit a static folder ready for Pages, Netlify, GitHub Pages, or any static host.

## Installation

```bash
npm install presto
```

You can also run the CLI directly with `npx presto` when your environment has access to npm.

## Usage

Generate a site for the current repository:

```bash
npx presto
```

Build a remote repository and write output to `./dist`:

```bash
npx presto jdorfman/awesome-json dist
```

Point at a GitLab project:

```bash
npx presto gitlab-org/gitlab-foss
```

Add analytics and a theme:

```bash
npx presto vercel/next.js ./public --ga G-123456789 --theme nord --palette dark
```

### Command options

| Flag | Description |
| ---- | ----------- |
| `--image <URL>` | Override the Open Graph/Twitter image URL. |
| `--ga <MEASUREMENT_ID>` | Inject Google Analytics. |
| `--theme <name-or-url>` | Fetch a CSS/HTML template from the Presto theme store (or a direct URL). |
| `--palette <palette>` | Optional palette suffix to combine with `--theme`. |
| `--verbose` | Log detailed progress information. |

## Development

Clone the repo and link the CLI locally:

```bash
git clone https://github.com/your-org/presto.git
cd presto
npm install
npm link
```

Now run `presto` inside any project directory to test changes.

## License

MIT
