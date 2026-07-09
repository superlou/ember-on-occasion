# Templates

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
