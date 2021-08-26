## astro react tailwind blog with tags on hosted on Azure Static Web Apps

1. make blog on github and clone to local machine
2. use azure vscode extension to add swa
3. `npm init astro --template blog-multiple-authors`
4. `npm i `
5. Update astro.config

```
export default ({
  buildOptions: {
    site: 'https://blog.duncanhunter.com.au'
  }
});
```

6. `npm run build && npm start -o`
7.

```
git add .
git commit -m "you commit message here..."
git push
```

8. add tailwind

```
const defaultTheme = require('tailwindcss/defaultTheme')

module.exports = {
  mode: "jit",
  purge: ["./public/**/*.html", "./src/**/*.{astro,js,jsx,ts,tsx,vue,svelte}"],
  theme: {
    extend: {
      fontFamily: {
        sans: ["Inter var", ...defaultTheme.fontFamily.sans],
      },
    },
  },
};

```

add tailwind with npm
` npm install tailwindcss@latest`
add tailwind astro build plugin to astro.config.js

```
  buildOptions: {
    tailwindConfig: './tailwind.config.js',
    site: 'https://blog.duncanhunter.com.au'
  }
```
rename global.scss to global.css and add tailwind imports and remove any existing styles
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
import global css file on MainHead.astro
```
    <link rel="stylesheet" href="https://rsms.me/inter/inter.css">

```
9. Change the title and discription on index.astro
```
let title = 'Duncan Hunter’s Blog';
let description = 'A blog about my work';
```

10.
add tailwind typography
```npm i -D @tailwindcss/typography```
update tailwinf config
```
module.exports = {
  mode: "jit",
  purge: ["./public/**/*.html", "./src/**/*.{astro,js,jsx,ts,tsx,vue,svelte}"],
  theme: {
    extend: {
      fontFamily: {
        sans: ["Inter var", ...defaultTheme.fontFamily.sans],
      },
    },
  },
  plugins: [require("@tailwindcss/typography")],
};
```