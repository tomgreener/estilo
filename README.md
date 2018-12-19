# estilo

### TODO

- Prefixing your variables with $color- allows code editors to list all colors when a user types $color- when declaring a color (e.g. $color-blue-sparkle: #0076ff;
$color-black: #000000, $color-pale-purple: #b089d5, $color-berta-blue: #4bdaff) => Do this for all relevant variables that people might be using
- Use CSS variables for horizontal/vertical rhythmn variables - this allows them to be easily changed client-side inside media query tags => will require https://github.com/jhildenbiddle/css-vars-ponyfill
- Suggest best practices for SCSS compilation (use post SCSS and use group media queries plugin)
```
postcss.config.js:

module.exports = {
  plugins: [
    require("autoprefixer")({}),
    require("css-mqpacker")({ sort: true }),
    require("postcss-combine-duplicated-selectors")({
      removeDuplicatedProperties: true
    }),
    require("cssnano")({})
  ]
};

webpack.config.js:

module: {
    rules: [
      {
        test: /\.scss$/,
        use: [
          MiniCssExtractWebpackPlugin.loader,
          "css-loader",
          "postcss-loader",
          "sass-loader"
        ]
      }
    ]
  },
```
