## Binding HTML class
+ You can pass an object to class binding
+ You can pass an **array** to class binding

```
<div class="static" v-bind:class="{ 'class-a': isA, 'class-b': isB }"></div>

//On the VM side
data: {
  isA: true,
  isB: false
}

//It gets renders
<div class="static class-a"></div>
```


#### This is how you directly bind an object to it
```
<div v-bind:class="classObject"></div>

data: {
  classObject: {
    'class-a': true,
    'class-b': false
  }
}
```


## Binding inline style
+ It looks like CSS, but it's actually an object
+ Vue.js can automatically prefix your CSS




```
<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>

data: {
  activeColor: 'red',
  fontSize: 30
}
```
