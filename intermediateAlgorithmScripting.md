# Intermediate Algorithm Scripting

### Sum All Numbers in a Range
Get passed an array of two numbers and return the sum of those numbers and all numbers between them
```javascript
function sumAll(arr) {
  let result = 0;
  if (arr[0] < arr[1]) {
    for (let x = arr[0]; x <= arr[1]; x++) {
      result = result + x;
    }
  } else {
    for (let x = arr[1]; x <= arr[0]; x++) {
      result = result + x;
    }
  } return result;
}

sumAll([1, 4]);
// returns 10
```
* First this function declares the variable 'result', then checks if the first or second number in the array is smaller
* Next it sets x equal to the smaller of the two numbers and iterates up to and including the larger number
* Every loop it adds x to result, and on completion returns result



### Dif Two Arrays
Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both.
```javascript
function diffArray(arr1, arr2) {
  var newArr = [];

//   for (let x = 0; x < arr1.length; x++) {
//     if (arr2.indexOf(arr1[x]) == -1) {
//       newArr.push(arr1[x]);
//     }
//   }
//   for (let x = 0; x < arr2.length; x++) {
//     if (arr1.indexOf(arr2[x]) == -1) {
//       newArr.push(arr2[x]);
//     }
//   }
//   return newArr;

  newArr = arr1.filter(x => arr2.indexOf(x) == -1);
  return newArr.concat(arr2.filter(x => arr1.indexOf(x) == -1));
}

diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]);
// returns [4]
```
* Note there are two solutions given here - one by me and one reworked with my roommate, world-renowned python programmer Jacky Chen
* 1st solution:
  * Run two for loops, each iterating through one of the two arrays using indexOf and checking if each of its elements returns a negative one a [x] index of the other array. If so, that means the number is not in the other array at any index and can be pushed to the new array
* 2nd solution:
  * create a new array from a filtered section of arr1 that checks for its elements in arr2 using index of and only passes elements that return -1
  * It then concatinates(sp?) newArr with a section of arr2 run through the same filter

