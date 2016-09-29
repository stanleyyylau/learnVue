# Keep in mind
Vue.js uses a DOM-based templating implementation. This means that all Vue.js templates are essentially valid, parsable HTML enhanced with some special attributes.

## Interpolations
+ Use Mustache syntax
+ Can only be used in raw html and attributes

### This is how you interpolate properties
```
<span>Message: {{ msg }}</span>

```


### This is how you interpolate raw html
```
<div>{{{ raw_html }}}</div>
```



## Binding expressions
+ It can translate Javascript expressions, but only one line each binding
+ It can also take arguments
+ Filter in this case will be super handy

```
{{ number + 1 }}
{{ ok ? 'YES' : 'NO' }}
{{ message.split('').reverse().join('') }}
```

### Filter example
```
{{ message | capitalize }}
```


## Directives
+ Directives start with ``v-`` and is used for making your html smart
+ Modifier at the end of directives indicate how directives should be bound (Useful in filter and such)


### Modifier example
```
<a v-bind:href.literal="/a/b/c"></a>
```


## Shorthands
+ will be super useful when you're building SPA where all your html are managed by Vue
+ Like ``v-bind`` and ``v-on``


``<a v-bind:href="url"></a>'`` becomes ``<a :href="url"></a>``

``<a v-on:click="doSomething"></a>`` becomes ``<a @click="doSomething"></a>``
