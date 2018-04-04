# Basci Algorithm Challenge Code

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
```
* This function checks if a string passed to it is a palindrome when just the alphanumeric characters are considered
* First we declare var noB and set it equal to the string with all non-alphanumeric characters removed and all the remaining charcters switched to lowercase
* Then we check if this noB variable is equal to itself in reverse order
* If so, we return true, otherwise return false

