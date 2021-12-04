# svelte-base-scss-prettier
svelte 기본 구축 scss, prettier 적용


## setting.json
```
"editor.formatOnType": true,
    "prettier.arrowParens": "avoid",
    "prettier.printWidth": 80,
    "prettier.tabWidth": 4,
    "prettier.singleQuote": true,
    "[svelte]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnPaste": true,
    "editor.formatOnSave": true,
```

## project root에 .prettierrc 만들기

```
{
  "svelteSortOrder": "scripts-styles-markup",
  "svelteStrictMode": true,
  "svelteBracketNewLine": true,
  "svelteAllowShorthand": false,
  "singleQuote": true,
  "semi": false,
  "tabWidth": 2,
  "trailingComma": "all",
  "printWidth": 100
}
```

## npm i --save-dev prettier-plugin-svelte prettier 

## node sass babel, 
```
npm install --save-dev svelte-preprocess sass
npm i --save-dev @babel/core @babel/preset-env @babel/plugin-proposal-optional-chaining

rollup.config.js

svelte({
      preprocess: sveltePreprocess({
        babel: {
          presets: [
            [
              "@babel/preset-env",
              {
                loose: true,
                modules: false,
                targets: { esmodules: true },
              },
            ],
          ],
        },
        plugins: ["@babel/plugin-proposal-optional-chaining"],
      }),
      compilerOptions: {
        // enable run-time checks when not in production
        dev: !production,
      },
    }),

```
