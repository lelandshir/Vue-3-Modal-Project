# Vue 3 & Firebase

### VSC Extensions

1. material icon theme
1. vetur
1. live server

### CSS

#### To compile the Vue `<style>` tag w/ Sass/SCSS:

- Say yes to using `CSS Preprocessors` when creating a Vue Project, select Dart-Sass to use things like `@use` and `@include`
- Install Sass:
  `npm i sass --save-dev`
- Create or add code to `vue.config.js`
- Add this code to it:

```
module.exports = {
	css: {
		loaderOptions: {
			sass: {
				implementation: require("sass"),
			},
		},
	},
};
```

- Note: Initially App's styles are globally scoped (they get placed in the head), restrict to just that component by adding the `scoped` prop to `<style>`

- Add `lang="sass"` to `<style>` in components
- In src, `mkdir styles`, `touch styles/global.sass`

### Vue Files

- main.js kickstarts the application by mounting the App component to the dom
- Components have `.vue` extension
- Components can contain 3 parts:

  1. HTML Template
  1. Script: Where we export the object (optional)
  1. Styles (optional)

- Exported Component Object can hold methods, data, etc
  1. If we want data, use the data function which returns an object
  1. Outputting Data: double curlys in the template similar to Angular 1
