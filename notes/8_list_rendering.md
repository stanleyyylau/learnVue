# List rendering
+ Like, conditional rendering, Vue do this in directive rather than template strings
+ Be aware of ``item in items`` syntax
+ You can access parent scope data and you'll be given a ``$index``
+ You can access the index as well as the key


```
<div v-for="(index, item) in items">
  {{ index }} {{ item.message }}
</div>

```


## Array change detection

### Mutation Methods
+ Using these methods in array will result in view update

### Replacing an array
+ ``filter()``, ``concat()``, ``slice()`` are non mutating methods
+ So you have to replace the original array with the returned array
+ track-by gives Vue a hint so that it can use existing instance as much as possible(U learn that from React)

**track-by example**
```
{
  items: [
    { _uid: '88f869d', ... },
    { _uid: '7496c10', ... }
  ]
}

```

**track-by $index**


## Caveat
+ ``$set()`` and ``$remove()`` methods are convenient array methods

## v-for used with object
+ instead of ``$index``, each scope will have access to something called ``$key``
+ You can also provide an alias for the key



## v-for used with range
+ can't think of a use case
+ take an integer and it will repeat the template that many times


```
<div>
  <span v-for="n in 10">{{ n }} </span>
</div>


```


## Display filtered/Sorted results
If you want to display a filtered or sorted version of the array with mutating the original one, you have two options

+ Computer properties
+ Use built-in ``filterBy`` and ``orderBy`` filters
