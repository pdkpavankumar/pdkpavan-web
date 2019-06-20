---
title: Different ways to remove/delete items from an array
category: "Javascript"
cover: photo-1490474418585-ba9bad8fd0ea.jpg
author: P D K Pavan Kumar
---

## Different ways to remove/delete items from an array

####**1. Length**
JavaScript array elements can be removed by setting length property less the array length. This approach will only remove the elements which are at the tail position.
```javascript
> arr = [1,2,3,4,5];
 (5) [1, 2, 3, 4, 5]
> arr.length = 3
 3
> arr
 (3) [1, 2, 3]
```
####**2. POP**
Pop method removes and returns the last element from the array.
```javascript
> arr = [1,2,3,4,5];
 (5) [1, 2, 3, 4, 5]
> value = arr.pop()
 5
> value
 5
> arr
 (4) [1, 2, 3, 4]
```
####**3. Shift**
Shift methods works same like pop only difference is instead of last element it removes the first element from the array.
```javascript
> arr = [1,2,3,4,5];
 (5) [1, 2, 3, 4, 5]
> value = arr.shift()
 1
> arr
 (4) [2, 3, 4, 5]
```
####**4. Splice**
Splice method is used to remove multiple sequential elements from an array.
```javascript
>arr = [1,2,3,4,5,6,7,8]
 (8) [1, 2, 3, 4, 5, 6, 7, 8]
> removedelements=arr.splice(2,2)
 (2) [3, 4]
> arr
 (6) [1, 2, 5, 6, 7, 8]
```
####**5.  Array Filter**
This is safe method. Unlike splice it will create a new array instead of mutating the original array.
```javascript
> arr = [1,2,3,4,5,6,7,8]
(8) [1, 2, 3, 4, 5, 6, 7, 8]
> newarr = arr.filter((ele) =>  (ele <3 || ele>4))
(6) [1, 2, 5, 6, 7, 8]
> arr
(8) [1, 2, 3, 4, 5, 6, 7, 8]
> newarr
(6) [1, 2, 5, 6, 7, 8]
```
####**6. Delete**
delete operator is used to delete a specific element from the array.
If you see the below code the array length is same and it makes the value undefined. this is happening because delete is designed to remove the properties in an object and array is also an object.

The reason the element is not actually removed from the array is the delete operator is more about freeing memory than deleting an element. The memory is freed when there are no more references to the value.
```javascript
>arr = [1,2,3,4,5]
 (5) [1, 2, 3, 4, 5]
>delete arr[2]
 true
>arr
 (5) [1, 2, empty, 4, 5]
>arr[2]
 undefined
```
####**7.  clear/reset**
Using this approaches we can clear the entire array. 

- assigning an empty array
```javascript
>arr = [1,2,3,4]
(4) [1, 2, 3, 4]
> arr
(4) [1, 2, 3, 4]
> arr = []
[]
> arr
[]
```
- making the array length to zero
```javascript
>arr = [1,2,3,4]
(4) [1, 2, 3, 4]
>arr.length
4
>arr.length = 0
0
>arr
[]
```
####**8. lodash**
we can always use 3rd party library methods to perform this operation. here i took lodash as an example.
lodash has remove method its syntax is similar to filter but the operation return matching elements.
```javascript
>arr = [1,2,3,4]
 (4) [1, 2, 3, 4]
>removedele = _.remove(arr, (ele) => ele!==2)
 (3) [1, 3, 4]
>arr
 [2]
> removedele
(3) [1, 3, 4]
```

--peace