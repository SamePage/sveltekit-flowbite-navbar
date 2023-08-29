# SvelteKit / flowbite-svelte / Navbar Bug

## Steps to create the project

### Install sveltekit

```bash
npm create svelte@latest navbar-bug
```

### Change to the created directory

```
cd navbar-bug
```

### install tailwindcss

```
npx svelte-add@latest tailwindcss
```

### run install

```
pnpm install
```

### install flowbite-svelte and related libs

```bash
pnpm install flowbite flowbite-svelte flowbit-svelte-icons classnames @popperjs/core
```

### edit the tailwind.config.cjs to make it as follows:

```javascript
/** @type {import('tailwindcss').Config}*/
const config = {
  content: [
    './src/**/*.{html,js,svelte,ts}',
    './node_modules/flowbite-svelte/**/*.{html,js,svelte,ts}',
  ],

  theme: {
    extend: {},
  },

  plugins: [require('flowbite/plugin')],
  darkMode: 'class',
};

module.exports = config;
```

### Added the +layout.svelte and +page.svelte files
