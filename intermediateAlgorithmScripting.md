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
  * Run two for loops, each iterating through one of the two arrays using indexOf and checking if each of its elements returns a negative one at [x] index of the other array. If so, that means the number is not in the other array at any index and can be pushed to the new array
* 2nd solution:
  * create a new array from a filtered section of arr1 that checks for its elements in arr2 using index of and only passes elements that return -1
  * It then concatinates(sp?) newArr with a section of arr2 run through the same filter

### Convert to Roman
Take a number and convert it to a roman numeral
This one is a doozy.
```javascript
// Try to find the largest roman variable smaller than the given num
// Push that number to romanString and subtract its value from given num
// repeat?

//let roman = {  M: 1000, D: 500, C: 100, L: 50, X: 10, V: 5, I: 1 }

function convertToRoman(num) {
  let tracker = num;
  let romanString = []

  if (tracker >= 1000) {
    for (tracker; tracker >= 1000;) {
      romanString.push("M");
      tracker = tracker - 1000;
    }
  }
  if (tracker >= 900) {
    romanString.push("CM");
    tracker = tracker - 900;
  }
  if (tracker >= 500) {
    for (tracker; tracker >= 500;) {
      tracker = tracker - 500;
      romanString.push("D");
    }
  }
  if (tracker >= 400) {
    romanString.push("CD");
    tracker = tracker - 400;
  }
  if (tracker >= 100) {
    for (tracker; tracker >= 100;) {
      tracker = tracker - 100;
      romanString.push("C");
    }
  }
  if (tracker >= 90) {
    romanString.push("XC");
    tracker = tracker - 90;
  }
  if (tracker >= 50) {
    for (tracker; tracker >= 50;) {
      tracker = tracker - 50;
      romanString.push("L");
    }
  }
  if (tracker >= 40) {
    romanString.push("XL");
    tracker = tracker - 40;
  }
  if (tracker >= 10) {
    for (tracker; tracker >= 10;) {
      tracker = tracker - 10;
      romanString.push("X");
    }
  }
  if (tracker >= 9) {
    romanString.push("IX");
    tracker = tracker - 9;
  }
  if (tracker >= 5) {
    for (tracker; tracker >= 5;) {
      tracker = tracker - 5;
      romanString.push("V");
    }
  }
  if (tracker >= 4) {
    romanString.push("IV");
    tracker = tracker - 4;
  }
  if (tracker >= 1) {
    for (tracker; tracker >= 1;) {
      romanString.push("I");
      tracker = tracker - 1;
    }
  }
//   romanString = '"' + romanString.join('').toString() + '"';
  return romanString.join('').toString();
}

convertToRoman(798);
returns "DCCXCVIII"
```
* I brute-forced my way through this solution. It's not elegant, it takes up tons of lines of code, and it's super slow to run for the computer
* The logic for the code is in the first two commented-out lines. It's simple reasoning and did work.  Going to re-try this problem with another solution below