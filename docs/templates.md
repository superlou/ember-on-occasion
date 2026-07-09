# Templates

Ember's templating language is a descendent of [Handlebars](https://handlebarsjs.com/).

Ember templates are most often found in files with the extension `.gjs` or `gts` (depending on whether you are using TypeScript or not) inside of `<template></template>`. This may be referred to as template tag or strict mode. There are other ways to use templates but we will not concern ourselves with those, for now.

## HTML

Templates are written in a component with HTML within the `<template>` tag.

```html
<template>
  <article>
    <h1>My title</h1>
    <!-- html comments stay where you put them -->
    <p>This is an article about...</p>
  </article>
</template>
```

## Expressions

```hbs
const name = 'Phil';

<template>
  <h1>Hi {{name}}</h1>
</template>
```

```hbs
const Person = { firstName: 'Phil', lastName: 'Gengler' };

<template>
  <h1>Hi {{Person.firstName}} {{Person.lastName}}</h1>
</template>
```

## Comments

```hbs
<template>
  {{! This is a comment }}
  {{!-- This is a comment that allows must}}ches --}}
</template>
```

## Escaping

```hbs
const specialChars = "& < > \" ' ` =";

<template>
  {{specialChars}} {{! outputs &amp; &lt; &gt; &quot; &#x27; &#x60; &#x3D; }}
  {{{specialChars}}} {{! outputs & < > " ' ` = }}
</template>
```

## Conditionals

```hbs
{{#if this.someThing}}
  Shown if someThing is true.
{{else if this.anotherThing}}
  anotherThing is true.
{{else if this.yetAnotherThing}}
  yetAnotherThing is true.
{{else}}
  If nothing else.
{{/if}}

<div class="{{if @isActive "is-active"}}">
  This div adds the "is-active" class based on the argument @isActive.
</div>
```

## Looping
Iterate over a list:

```hbs
<ul>
  {{#each-in this.records as |record|}}
    <li>{{record}}</li>
  {{else}}
    Shown if this.records is empty, null, or undefined.
  {{/each}}
</ul>
```

Iterate over a dictionary:

```hbs
<ul>
  {{#each-in this.dict as |key value|}}
    <li>{{key}} - {{value}}</li>
  {{/each}}
</ul>
```
