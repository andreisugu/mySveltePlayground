# My Svelte Playground

A minimal, lab-style Svelte + Vite + Tailwind CSS project with a simple button and input form.

## What's This?

A experimental playground built with:
- **Svelte** - Reactive UI framework
- **Vite** - Lightning-fast bundler
- **Tailwind CSS** - Utility-first styling

Live demo: https://andreisugu.github.io/mySveltePlayground/

## Features

- Simple input field to capture text
- Button that displays what you typed
- Dark theme with blue accents
- Deployed to GitHub Pages via GitHub Actions

## Tech Stack

- Svelte 4
- Vite 8 (beta)
- Tailwind CSS
- Node 20+
- npm 10+

## Project Structure

```
src/
├── App.svelte      # Main component with input + button
├── main.js         # Entry point
└── app.css         # Global styles with Tailwind directives

index.html          # HTML entry point
vite.config.js      # Vite config
tailwind.config.js  # Tailwind config
svelte.config.js    # Svelte config
```

## Development

```bash
npm install
npm run dev
```

This starts a dev server at `http://localhost:5173/`

## Build for Production

```bash
npm run build
```

Output goes to `dist/`

## Deployment

The site automatically deploys to GitHub Pages when you push to `main` via GitHub Actions.

The workflow builds the project and pushes to the `gh-pages` branch.

## Extending

Want to add more components? Create `.svelte` files in `src/lib/` and import them into `App.svelte`.

Modify `App.svelte` to experiment with:
- More input types (checkbox, select, etc.)
- State management
- Event handling
- Component composition

## License

MIT - See [LICENSE](LICENSE) for details
