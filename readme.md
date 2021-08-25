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
