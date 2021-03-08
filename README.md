# Vue 3 & Firebase

### VSC Extensions

1. material icon theme
1. vetur
1. live server

#### To compile the Vue `<style>` tag w/ Sass/SCSS:

1. Say yes to using `CSS Preprocessors` when creating a Vue Project, select Dart-Sass to use things like `@use` and `@include`
1. Install Sass:
   `npm i sass --save-dev`
1. Create or add code to `vue.config.js`
1. Add this code to it:

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

1. Add `lang="sass"` to `<style>` in components
