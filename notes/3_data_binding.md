# Keep in mind
Vue.js uses a DOM-based templating implementation. This means that all Vue.js templates are essentially valid, parsable HTML enhanced with some special attributes.

## Interpolations
+ Use Mustache syntax
+ Only be used in raw html and attributes

## Binding expressions
+ It can translate Javascript expressions, but only one line each binding
+ It can also take arguments

```
{{ number + 1 }}
{{ ok ? 'YES' : 'NO' }}
{{ message.split('').reverse().join('') }}
```

## Directives
+ Directives start with ``v-`` and is used for making your html smart
+ Modifier at the end of directives indicate how directives should be bound


## Shorthands
+ will be super useful when you're building SPA where all your html are managed by Vue
+ Like ``v-bind`` and ``v-on``
