# Vue 3 & Firebase

### VSC Extensions

1. material icon theme
1. vetur
1. live server

### CSS

#### To compile the Vue `<style>` tag w/ Sass/SCSS and Solving the `TypeError: this.getOptions is not a function in vue.js`

- Say yes to using `CSS Preprocessors` when creating a Vue Project, select Dart-Sass to use things like `@use` and `@include`
  Fixing the TypeError with Sass

npm i -D sass sass-loader
in package.json: `devDependencies: “sass-loader”: “7.3.1”,`
remove node_modules
npm i
My `package.json` file:

```
 "devDependencies": {
    "@vue/cli-plugin-babel": "~4.5.0",
    "@vue/cli-plugin-eslint": "~4.5.0",
    "@vue/cli-service": "~4.5.0",
    "babel-eslint": "^10.1.0",
    "eslint": "^6.7.2",
    "eslint-plugin-vue": "^6.2.2",
    "sass": "^1.32.6",
    "sass-loader": "7.3.1",
    "vue-template-compiler": "^2.6.11"
  },
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

### Template Refs

- Template refs are for handling DOM elements, like the query selector

### Passing Props

- Make components more reusable
- Data Bind to set props as different data types using a `:`
- Output dynamic classes with data binding

### Custom Events

- An event can be fired from a component and listened to by the parent component
- Emit the event

### Event Modifiers

- React to a right click instead of a left OR only react to a click event if a user clicks on a specific element
- React only in certain condition, stop event bubbling
- Ex: `@click.shift` only react wen the user clicks while holding down the shift key or `@click.self`

### Slots

- Really good for passing custom templates into reusable components
- Very different from props
- named slots using template tag
- Perfect for passing links into a modal
- Default content [demo]

### Teleport (new feature)

- Teleport some content to a different place in the dom, even in outside the scope of the Vue app itself
