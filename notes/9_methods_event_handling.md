## Method handler
+ You can use ``<button v-on:click='greet'>Click Me</button>``
+ Your methods must defined under the method object of Vue instance

```
<div id="example">
  <button v-on:click="greet">Greet</button>
</div>

```

**You can also use an inline javascript handler**
+ This fancy long sentence simply means ``pass value to it``
+ You can pass ``$event`` in the inline handler so you can access original DOM event

```
<div id="example-2">
  <button v-on:click="say('hi')">Say Hi</button>
  <button v-on:click="say('what')">Say What</button>
</div>

```


**Example with $event**

```
<button v-on:click="say('hello!', $event)">Submit</button>

// On the JS side
// ...
methods: {
  say: function (msg, event) {
    // now we have access to the native event
    event.preventDefault()
  }
}

```


## Event modifiers
+ ``.prevent`` and ``.stop`` event modifier is super cool
+ Vue is doing this so you only have to purely deal with **data logic** rather than DOM event details


```
<!-- the click event's propagation will be stopped -->
<a v-on:click.stop="doThis"></a>
<!-- the submit event will no longer reload the page -->
<form v-on:submit.prevent="onSubmit"></form>
<!-- modifiers can be chained -->
<a v-on:click.stop.prevent="doThat">
<!-- just the modifier -->
<form v-on:submit.prevent></form>

```


## Key modifiers
+ Useful for listening to keyboard events
+ Vue.js provides aliases like ``<input v-on:keyup.enter="submit">`` and ``<input @keyup.enter="submit">``


## Conceptual aside: why listener in HTML?
+ By looking at template, you'll know what that handler is in JS
+ No event listen and JS, you ViewModel is pure logic and DOM free, that makes it easier to test
+ When ViewModel are destroyed, all event listener will be removed. good for performance. those weird ``v-whatever`` things will be custom html attributes
