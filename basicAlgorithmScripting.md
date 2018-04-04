# Basic Algorithm Challenge Code

### Reverse a String
```javascript
function reverseString(str) {
  return str.split('').reverse().join('');
}

reverseString("hello");
// returns "olleh"
```
* This function  takes a string, splits it by every character, reverses the order, and rejoins the string to get its output

### Factorialze a number
```javascript
function factorialize(num) {
  var prev_num = 1;
  for (var j = 1; j <= num; j++) {
    prev_num = prev_num*j;
  }
  return prev_num;
}

factorialize(5);
// returns 120
```
* This function iterates through a variable called 'j' while it is less than or equal to the nu,ber being passed to it
* It increments j and multiplies it by a variable called 'prev_num', which it sets equal to itself times j

### Check for Palindromes
```javascript
function palindrome(str) {
  var noB = str.replace(/[^0-9a-z]/gi, '').toLowerCase();
  if (noB == noB.split('').reverse().join('')){
    return true;
  } else {
    return false;
  }
}

palindrome("_eye");
// returns "true"
```
* This function checks if a string passed to it is a palindrome when just the alphanumeric characters are considered
* First we declare var noB and set it equal to the string with all non-alphanumeric characters removed and all the remaining charcters switched to lowercase
* Then we check if this noB variable is equal to itself in reverse order
* If so, we return true, otherwise return false

### Find the Longest Word in a String
```javascript
function findLongestWord(str) {

  var poop = str.split(" ");
  var long = "";

  for (var j =0; j < poop.length; j++) {
    if ( poop[j].length >= long.length) {
      long = poop[j];
    }
  }
  return long.length;
}

findLongestWord("The quick brown fox jumped over the lazy dog");
// returns 6
```
* This function returns the length (read 'number') of longest word in a string
* Takes a string, splits it by spaces, and declares an empty variable named 'long'
* It then iterates through each word in the string and checks it against long. if it's longer than the length of 'long', it sets long to that word
* Finally, it returns long.length, which will be the length of the longest word in the string

### Title Case a Sentence
```javascript
function titleCase(str) {
  return str[0].toUpperCase()+str.toLowerCase().replace(/\s\w/g, l => l.toUpperCase()).slice(1);
}

titleCase("I'm a little tea pot");
// returns "I'm A Little Tea Pot"
```
* This function returns a string where the first letter of each word is capitalized and the rest are lowercase
* It returns the first character of the string capitalized with the rest of the string made lowercase with the first letter of each word after capitalized and sliced into the array before the first index

### Return Largest Numbers in Arrays
```javascript
// get array with 4 nested arrays
// find largest number in each array
// push largest number to big_arr
// return big_arr



function largestOfFour(arr) {
  var big_arr = [];

  //This iterates through both the top-level & second level array
  for (var j = 0; j < arr.length; j++) {
    big_arr.push(Math.max.apply(null, arr[j]));
  }
  return big_arr;
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
// returns [5,27,39,1001]
```
* This function gets an array of nested arrays, iterates through each, applying Math.max to them and pushing the return to a new array, which we then return

### Confirming the Ending
```javascript
function confirmEnding(str, target) {
  // console.log(-target.length); this works
  return (str.substr(-target.length) === target);
}

confirmEnding("Bastian", "n");
// returns true
```
* end