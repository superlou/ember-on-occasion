# Components

All components, regardless of being "template-only" or "class-based" are created in `app/components`.

## Template-only components

Template-only components use the `.gjs` extension and wrap the contents in a `<template>` tag. They are the recommended way to create components, even without component logic. 

```html
<!-- banner-hero.gjs -->
<template>
    <div class="banner-hero">
        <img src={{@image}}>
    </div>
</template>
```

There is nothing wrong with template-only components. Nobody should use `.hbs` files (without a `<template>` tag) anymore.

## Class-based components

These components use the `.gjs` extension and combine logic with the template. The template must be inside a `<template>` tag.

```js
// banner-hero.gjs
import Component from '@glimmer/component';

export default class BannerHero extends Component {
  get imageWithDefault() {
    return this.args.image ?? "/default_hero.jpg";
  }

  <template>
    <div class="banner-hero">
        <img src={{this.imageWithDefault}}>
    </div>
  </template>
}
```

Arguments passed to the component are accessible *read-only* in `this.args`.
