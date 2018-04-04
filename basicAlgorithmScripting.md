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
* This function takes two arguments and checks if the last character in a string matches the second argument
* It does this with str.substr, which allows you to select a substring by its negative index (how far back from the end it is)
* We take the substring equal to the length of the second argument and check if they're the same

### Repeat a String Repeat a string
```javascript
function repeatStringNumTimes(str, num) {
  var str2 = "";
  for (var j = 0; j < num; j++) {
    str2 = str2.concat(str);
  }
  return str2;
}

repeatStringNumTimes("abc", 3);
// returns 'abcabcabc'
```
* This function returns a new string equal to the original string repeated a specified number of times
* We do this by concatinating the original string onto the new string while var j is less than the number passed to the function

### Truncate a String
```javascript
function truncateString(str, num) {
  if (str.length > num && num > 3) {
    str = str.slice(0, num-3) + "...";
  } else if (num < 3) {
    str = str.slice(0, num) + "...";
  }
  return str;
}

truncateString("A-tisket a-tasket A green and yellow basket", 11);
// returns "A-tisket..."
```
* This function checks if a string is greater than a given number and then shortens the string so that it + '...' is shorter than the number
* EXCEPTION - if the number given is 3 or less, the '...' don't count in its length
* If does this by setting the string equal to a slice of the string starting at the 0th index through the num-3 (or num if num < 3), adding '...', and returning the string

### Chunky Monkey (Chunking Arrays)
```javascript
function chunkArrayInGroups(arr, size) {
  var new_arr = [];
  for (var j = 0; j < arr.length; j += size) {
   new_arr.push(arr.slice(j, size+j));
  }
  return new_arr;
}

chunkArrayInGroups([0, 1, 2, 3, 4, 5, 6, 7, 8], 4);
// returns [[0,1,2,3],[4,5,6,7],[8]]
```
* This function takes two arguments, an array and a size to 'chunk' it into
* Declares new array and iterates through the old array, pushing slices of the array from 'j' index to j + 'size' (the size of our chunks)
* The trick here is not iterating by 1, but by the second argument in the for loop

### Slasher Flick
```javascript
function slasher(arr, howMany) {
  return arr.splice(howMany);
}

slasher([1, 2, 3], 2);
// returns [3]
```
* Returns remaining elements of an array after chopping off 'n' elements from the head
* Pretty simple, just makes use of splice, which returns a new array staring 'howMany' items from the start

### Mutations
```javascript
function mutation(arr) {
  let [a, b] = arr.map(x=>x.toLowerCase());
  let x = [...b].filter(x => a.search(x) !== -1 ? true : false);
  return x.length == arr[1].length ? true : false;
}

mutation(["HELLO", "hello"]);
// returns true
```
* Returns true if the string in the first element of the array contains all of the letters of the string in the second array element
* Function delcares a new array = the argument made lowercase (prevents false negatives from uppercase)
* It then declares var x and sets it equal to the elements of the arr[b] that have an equivalent in arr[a]
  * It iterates through b using a 'spread operator'
* Finally, if checks if the length of x is = arr[a].length
  * If it is, then all letters returned 'true' in the filter step, and all letters are present

### Falsy Bouncer
```javascript
bouncer = arr => {
  let new_arr = arr.filter(Boolean);
  return new_arr;
};

bouncer([7, "ate", "", false, 9]);
// returns [7, "ate", 9]
```
* Simple function that returns a new array equal to the old array filtered for any values that are falsy
* Just used filter to remove any values that dont return true in a boolean equation

### Seek and Destroy
```javascript
function destroyer() {
  const args = Array.from(arguments);
  var set = new Set(args.slice(1));
  return args[0].filter(x => !(set.has(x)));
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
// returns [1, 1]
```
* Given an array and arguments, return the array with arguments removed
* Creates an array (args) containing the original array and the other arguments => [[1, 2, 3, 1, 2, 3], 2, 3]
* Creates a variable equal to args minus the array we're checking arguments against (i.e. var set = what we want to remove from array)
* Returns the array with anything from the var we created filtered out

### Where Do I Belong
```javascript
function getIndexToIns(arr, num) {
  // r_s = running sum
  return arr.reduce((r_s, val) => r_s + (val < num ? 1 : 0) , 0);
}

getIndexToIns([2, 5, 10], 15);
// returns 3
```
* Function returns the lowest index at which a value should be inserted into an array once sorted
* Makes use of arr.reduce to iterate through the function, adding 1 or 0 to r_s depending on if the value of the arr at any index is less than the number we're trying to place
* This will return a number equal to the index the number should be added to the array

### Caesar's Cipher
```javascript
function rot13(str) { // LBH QVQ VG!

  let new_str = "";

  for (let x = 0; x < str.length; x++) {
    if (/[A-Z]/.test(str.charAt(x))) {
      if (str.charCodeAt(x) < 78) {
        new_str += String.fromCharCode(str.charCodeAt(x)+13);
      } else {
        new_str += String.fromCharCode(str.charCodeAt(x)-13);
      }
    } else {
      new_str += str.charAt(x);
    }
  } return new_str;
}
```
* This function takes a string that has been run through a caesar cipher and unciphers it.
  * https://en.wikipedia.org/wiki/ROT13
* Declares a new string and then iterates through the old string
* While running through old string, it tests each character. If the character is a letter, it checks what its charCode (unicode representation of a letter) is
* If charCode is less than 78 ('N'), it adds 13 to the charcode and pushes that new character onto the new string
* If charCode is greater than 78 (N), it subtracts 13 and adds that to new string
* If character is not a letter, it passes it as is to the new string






