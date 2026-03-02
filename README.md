
---

# My Svelte Playground

A minimal, lab-style Svelte + Vite + Tailwind CSS project with two example pages: a Study Goal form and a Simple Demo.

## What's This?

A experimental playground built with:
- **Svelte** - Reactive UI framework
- **Vite** - Lightning-fast bundler
- **Tailwind CSS** - Utility-first styling

Live demo: https://andreisugu.github.io/mySveltePlayground/

## Features

- **Study Goal Form**: Enter your name and a weekly study goal, then save and see your submission. Includes validation, live character counter, and reset.
- **Simple Demo Page**: The absolute simplest Svelte+Tailwind feature: type in a box, see it instantly below. No validation, no extras—just the basics.
- **Page Switcher**: Toggle between the two pages using the buttons at the top.
- **Dark theme**: Styled with Tailwind CSS v4 utility classes.
- **Deployed to GitHub Pages**

## Tech Stack

- **Svelte 4** – The reactive UI framework used for building the app.
- **Vite 8 (beta)** – The fast development server and build tool.
- **Tailwind CSS** – Utility-first CSS framework for styling.
- **Node.js 20+** – Required to run Vite, Svelte, and Tailwind tools. Node provides the JavaScript runtime for all build and dev scripts.
- **npm 10+** – The package manager for installing dependencies and running scripts (like `npm run dev` or `npm run build`).


## Project Structure

```
src/
├── App.svelte        # Main component, page switcher, and Study Goal form
├── SimplePage.svelte # Simplest demo page (input + display)
├── main.js           # Entry point
└── app.css           # Global styles, imports Tailwind v4
```

## How it Works

This project demonstrates a basic Svelte form with live feedback and validation, styled using Tailwind CSS v4. It is designed to be as beginner-friendly and minimal as possible, while still showing real-world Svelte and Tailwind usage.

**Key Svelte concepts shown:**
- Two-way binding (`bind:value`)
- Reactive statements (`$: ...`)
- Form submit and reset handlers
- Conditional rendering (`{#if ...}`)

**Key Tailwind concepts shown:**
- Utility classes for layout, color, and spacing
- Tailwind v4 integration via the official Vite plugin
## Beginner Guide

1. **Install dependencies:**
	```bash
	npm install
	```
2. **Start the dev server:**
	```bash
	npm run dev
	```
	Open the printed URL (usually http://localhost:5173) in your browser.
3. **Try the features:**
	- Use the buttons at the top to switch between the Study Goal Form and the Simple Demo page.
	- On the Study Goal Form: Enter your name and a study goal (max 120 characters), then click "Save Goal" to see your submission. If you leave a field empty or go over the character limit, you'll see an error message. Click "Reset" to clear the form.
	- On the Simple Demo page: Just type in the box and see your text instantly below—no validation, no extras.
4. **Explore the code:**
	- The Study Goal Form and page switcher are in `src/App.svelte`.
	- The Simple Demo is in `src/SimplePage.svelte`.
	- Styles are in `src/app.css` (using Tailwind v4).
	- Configuration is in `vite.config.js` and `tailwind.config.js`.

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

Modify `App.svelte` or add new `.svelte` files to experiment with:
- More input types (checkbox, select, etc.)
- State management
- Event handling
- Component composition

Or try adding a new feature, like a priority dropdown, a todo list, or another minimal page!

## License


MIT - See [LICENSE](LICENSE) for details

---

## How to Recreate This Project from Scratch

Want to build this same Svelte + Vite + Tailwind v4 project yourself? Here’s how:

1. **Create a new Vite + Svelte project:**
	```bash
	npm create vite@latest my-svelte-app -- --template svelte
	cd my-svelte-app
	```
2. **Install dependencies:**
	```bash
	npm install
	```
3. **Add Tailwind CSS v4 and its Vite plugin:**
	```bash
	npm install -D tailwindcss@^4 @tailwindcss/vite postcss autoprefixer
	npx tailwindcss init
	```
4. **Configure Tailwind:**
	- In `tailwind.config.js`, set:
	  ```js
	  export default {
		 content: ['./src/**/*.{html,js,svelte,ts}'],
		 theme: { extend: {} },
		 plugins: [],
	  }
	  ```
5. **Import Tailwind in your CSS:**
	- In `src/app.css`, replace everything with:
	  ```css
	  @import "tailwindcss";
	  ```
6. **Update Vite config:**
	- In `vite.config.js`, add the plugin:
	  ```js
	  import tailwindcss from '@tailwindcss/vite';
	  // ...existing code...
	  export default defineConfig({
		 plugins: [tailwindcss(), svelte()],
		 // ...existing config...
	  });
	  ```
7. **Replace `App.svelte` with your form code.**
8. **Run your app:**
	```bash
	npm run dev
	```

You now have a working Svelte + Vite + Tailwind v4 project, just like this one!
