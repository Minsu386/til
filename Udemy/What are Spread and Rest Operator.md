The spread and rest operators actually use the same syntax: `...` 

Yes, that is the operator - just three dots. It's usage determines whether you're using it as the spread or rest operator.

**Using the Spread Operator:**

The spread operator allows you to pull elements out of an array (=> split the array into a list of its elements) or pull the properties out of an object. Here are two examples:
```JavaScript
const oldArr = [1, 2, 3];
const newArr = [...oldArr, 4, 5]; //  now [1,2, 3, 4, 5];
```


Here's the spread operator used on an object:
```JavaScript
const oldObj = {
  name: 'Max';
};
const newObj = {
  ...oldObj, 
  age: 28
}
```
The `newObj` would then be
```JavaScript
{
  name: 'Max',
  age: 28
}
```
The spread operator is extremely useful for cloning arrays and objects. Since both are [reference types (and not primitives)](https://youtu.be/9ooYYRLdg_g), copying them safely (i.e. preventing future mutation of the copied original) can be tricky. With the spread operator you have an easy way of creating a (shallow!) clone of the object or array.