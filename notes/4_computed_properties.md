## Basic example
+ Make sure you don't fucking change computed properties!!!
+ They should be computed automatically according to raw data!!!

The reason why you should use this is because it's just like querying a database, what you're querying is dynamic according to the changes of the raw data. you don't want to store them, you query them when you need them, and when raw data changes, the computed value will be automatically changed as well.


```
var vm = new Vue({
  el: '#example',
  data: {
    a: 1
  },
  computed: {
    // a computed getter
    b: function () {
      // `this` points to the vm instance
      return this.a + 1
    }
  }
})
```

## Computed properties VS $.watch
+ Computer properties are cleaner where in $.watch you have to watch to variables


## You can set computed setter
+ It's great!!!
+ But I'm not sure when to use it.


```
computed: {
  fullName: {
    // getter
    get: function () {
      return this.firstName + ' ' + this.lastName
    },
    // setter
    set: function (newValue) {
      var names = newValue.split(' ')
      this.firstName = names[0]
      this.lastName = names[names.length - 1]
    }
  }
}
```
