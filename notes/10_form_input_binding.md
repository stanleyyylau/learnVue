## Basics Usage
``v-model`` is a good example of two-way data binding. it's just syntax sugar for getting value from user input event and update it to Vue instance under the data object

+ ``text`` and ``textarea`` binding
+ Pay close attention to `` <input type="checkbox" id="checkbox" v-model="checked">``
+ When binding multiple input elements, you might want to bind them to the same array and use expression filter


## Value binding
+ If the input has a ``value`` attribute, the ``v-model`` is going to bind the that value
+ If you want to bind to a dynamic property on Vue instance, you can use ``v-bind``

```
<input
  type="checkbox"
  v-model="toggle"
  v-bind:true-value="a"
  v-bind:false-value="b">

  // when checked:
  vm.toggle === vm.a
  // when unchecked:
  vm.toggle === vm.b
```
