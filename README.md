# **_Clonning in Javascript_**

**What is Clonning?**
In plain words, Clonning is either making a copy of the existing block of memory or creating another reference that points to the existing block of memory.
<br>
**Note:** _Here "Block of memory" can be any defined Object in Javascript._

**Why do we use Clonning ?**<br>
To create a copy of Existing Object instead of creating the same object from the scratch.<br>
Added Benifits:<br>
* To reduce our work in Manual-Copying.
* To reduce errors, caused due to Manual-Copying.

**What are the types of Clonning ?**

In JS, Clonning is of two types :

1. **Shallow Clonning**
    * Creates an extra reference to the existing Block of Memory (Object).
    * Separate memory is not allocated.
    * Change in block of memory(Object) affects all the reference pointers that are pointing to it.

2. **Deep Clonning**
    * Creates another copy of the existing Block of Memory (Object).
    * Separate memory is allocated.
    * Change in a block of memory(Object) does not affect other reference pointers as they both are different Blocks of Memory.

Consider this Example:
```js
function jsonCopy(src) {                    //Function returning a new object copied using src object
  return JSON.parse(JSON.stringify(src));
}

const source = {a:1, b:2, c:3};             //Creating source object
const deepCopy = jsonCopy(source);          //Creating an object using deep Clone.
const shallowCopy = source;                 //Creating an object using shallow Clone.

console.log(target);                        // output: {a:1, b:2, c:3}
source.a = 'a';                             // Changing the value of 'a' in source object

console.log(source.a);                      // output: 'a' Value Changed
console.log(deepCopy.a);                    // output: 1   Value did not Change
console.log(shallowCopy.a);                 // output: 'a' Value Changed
```

Here in this above example,
When the value of 'a' is changed from a to 1 of source object, there is a change in the value of a in shallowcopy object but not in the deepCopy object. This is caused because the shallowCopy object was reffering to the same Source Object and hence the change was seen.

![pic1](https://miro.medium.com/max/488/0*RGt-o4ovYiIt_9nS.)

_Image to depict the differences between Shallow and Deep Clone._

**What are the ways to Clone?**

Clonning can be done in JS either making it a shallow copy or a deep copy. The usual methods followed are:

1. Using Object.assign method.
2. Using Spread (...) operator.
3. Using Equal to (=) operator.
4. Using Json Methods.
5. Using _.deepclone() from loadash library.
