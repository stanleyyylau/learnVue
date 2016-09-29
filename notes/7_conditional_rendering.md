# Different between directive and string templates(Handlerbars)

### How handleBars do conditional rendering
```
<!-- Handlebars template -->
{{#if ok}}
  <h1>Yes</h1>
{{/if}}

```

### How the directive approach look like
```

<h1 v-if="ok">Yes</h1>

// Else block is also supported
<h1 v-if="ok">Yes</h1>
<h1 v-else>No</h1>

```



## Important conditional directives
+ Template v-if
+ v-if
+ v-show (No template syntax support)
+ v-else (else block for v-if/v-show)


## Component caveat
+ When used with components and v-show, v-else doesn’t get applied due to directives priorities

Code sample
```
<custom-component v-show="condition"></custom-component>
<p v-else>This could be a component too</p>

```

Instead you should do

```
<custom-component v-show="condition"></custom-component>
<p v-show="!condition">This could be a component too</p>

```


## v-if vs. v-show
In a word, v-if has higher toggle costs while v-show has higher initial render costs. So prefer v-show if you need to toggle something very often, and prefer v-if if the condition is unlikely to change at runtime.
