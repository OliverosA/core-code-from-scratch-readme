# core-code-from-scratch-readme

# Week 1 challenges

## Tuesday

1. ***Explanation about Interpreted And Compiled Programming Languages***
> A interpreted programming language is that one when the instructions are **executed at real time**. The compiled programming language **translate the high level language to low level language or machine code** before you can see the results, this can be little annoying when you make a mistake or when you need to change something in the code because you need to re compiled all the file again.


2. ***Is Java compiled or interpreted, or both?***

> Java is both, because the first step in every java source code is compiled and create an bytecode, then this bytecode need an interpreter for been executed in any platform

3. ***Pseudocode Currency Converter exercise***

> 1. START
> 2. USD <-- GET
> 3. BTCprice <-- 44727.56
> 4. Total <-- USD * BTCprice
> 5. PRINT Total
> 6. END

## Wednesday

### Date Of Birth In Binary

> My Date of birth is: 1996

### Binary Table

| 2^10 | 2^9 | 2^8 | 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|   1  |  1  |  1  |  1  |  1  |  0  |  0  |  1  |  1  |  0  |  0  |

`Date Of Birth In Binary: 11111001100`

### MIPS Challenges

1. Create a program that adds any two given numbers provided by the user

```assembly
  .data
	number1: .asciiz "\n Input the first number: "
	number2: .asciiz "\n Input the second number: "
	result: .asciiz "\n The Result is: "
	
.text
	main:
	
	li $v0, 4
	la $a0, number1 	#Showing the first message input
	syscall
	
	li $v0, 5 		#Catching the first number input
	syscall
	
	move $t0, $v0 		#Storing first input in t0
	
	li $v0, 4
	la $a0, number2 	#Showing the second message input
	syscall
	
	li $v0, 5 		#Catching the second number input
	syscall
	
	move $t1, $v0 		#Storing second input in t1
	
	add $t2, $t0, $t1 	#Adding the 2 numbers
	
	li $v0, 4
	la $a0 result 		#Showing the result message
	syscall
	
	li $v0, 1
	move $a0, $t2 		#Showing the operation result
	syscall
```

2. Create a program that displays your name

```assembly
  .data
	message: .asciiz "\n My name is: "
	name: .asciiz "Dorian Aldair Oliveros Botzock"
	
.text
	main:
	li $v0, 4
	la $a0, message 		#Showing the message
	syscall
	
	li $v0, 4
	la $a0, name 			#Showing my full name
	syscall
```

## Thursday

1. `Print special numbers:` In this exercise you must use an iterative flow control to be able to print all the even numbers in the range of numbers from 0 to 100. Remember that you should not print each number, you should use a flow control structure to perform the exercise.

```Javascript
/* 
===========================
        Using For
===========================
*/
var result = null;   //this variable will store the even numbers

for (var i = 0; i <= 100; i++) {
    
    if((i % 2) == 0){
        result = result + i + ' ';
    }

}

//Showing all the even numbers in console
console.log('The even numbers using FOR, from 0 to 100 are: ' + result);


/* 
===========================
        Using While
===========================
*/

result = null;      //setting the result null again
var number = 0;     //initializing number from 0

while (number <= 100) {

    if((number % 2) == 0 ){
        result = result + number + ' ';
    }
    
    number++;
}

//Showing all the even numbers in console
console.log('The even numbers using WHILE, from 0 to 100 are: ' + result);


/* 
===========================
        Using DO WHILE
===========================
*/

result = null;      //setting the result null again
number = 0;         //initializing number from 0

do {
    
    if((number % 2) == 0 ){
        result = result + number + ' ';
    }
    
    number++;
} while(number <= 100);

//Showing all the even numbers in console
console.log('The even numbers using DO WHILE, from 0 to 100 are: ' + result);
```

2. `Bad Code:` The code shown below is not working in the right way, as a task you must find the error made by the developer who programmed this code and correct it, for this exercise you must explain what the error is and place the correct code.

```Javascript
/*
first of all, the structure of the conditional if is wrong, 
it should be as follows 'if (cond = true)' using only 2 parentheses
secondly, within the 'if' condition an assignment was made and not an equalization 
so the code was changed from '(cond = true)' to '(cond == true)'
*/

var cond = false;

if (cond == true) {
  console.log('The cond variable is true');
} 
else {
  console.log('The cond variable is false');
}
```

3. `Bad Code 2:` You must create the code that follows the following logic, if the given number is 100, take this number as special and show the following message: "This is a special number!", but if the number is less than 1000, multiple of 10 and different from 100, you must show the following message: "This number is almost special". if none of the given conditions are met show the following message: "Just a regular number". Another developer was trying to program the logic, but apparently couldn't, you need to fix the code to work properly.

```Javascript
var n = 1000; //using another number to check the other conditionals

if (n == 100) {
  console.log('This is a special number!');
}
else if (n < 1000 && (n % 10) == 0 && n != 100) {
  console.log('This number is almost special');
} 
else {
  console.log('Just a regular number');
}
```

# Week 2 challenges

## Tuesday

1. `Multiply`

```Javascript
function multiply(a, b){
  return a * b;
}

```

2. `ASCII Total`

```Javascript
function uniTotal (str) {
  let total = 0;  
  let length = str.length;  //getting the total length of the string 
  for(let i = 0; i < length; i++){
    total += str[i].charCodeAt();
  }
  return total;
}
```

3. `Char From ASCII Value`

```Javascript
function getChar(c){
  return String.fromCharCode(c)
}
```

4. `Binary Addition`

```Javascript
function addBinary(a,b) {
  //using toString(2) to obtain the binary value of the number
  return (a+b).toString(2);
}
```
5. `Student's Final Grade`

```Javascript
function finalGrade (exam, projects) {
  let total = 0;
  if (exam > 90 || projects > 10) {
    total = 100;
  } else if (exam > 75 && projects >= 5) {
    total = 90;
  } else if (exam > 50 && projects >= 2) {
    total = 75;
  }
  return total;
}
```

## Wednesday

1. `Holiday VIII - Duty Free`

```Javascript
function dutyFree(normPrice, discount, hol){
  //getting the discount price
  let discountPrice = (normPrice * discount) / 100;
  //total of bottles at discount price to cover holiday cost
  let totalBottles = hol / discountPrice;
  //returning an integer Round Down
  return Math.floor(totalBottles);
}
```

2. `Twice As Old`

```Javascript
function twiceAsOld(dadYearsOld, sonYearsOld) {
  return Math.abs(dadYearsOld - sonYearsOld * 2);
}
```

3. `Valid Spacing`

```Javascript
function validSpacing(s) {
  let spaceCounter = 0; //counter for spaces
  let nonSpaceCounter = 0; //counter for everything that is not a space
  //verifying the start and the end of the string
  if(s[0] === ' ' || s[s.length - 1] === ' ') return false;
  
  for(let i = 0; i < s.length; i++){
    if (s[i] === ' '){
      spaceCounter++;
      nonSpaceCounter = 0;
      if(spaceCounter > 1){ //if the string has two or more spaces in a row 
        return false;
      }
    }
    if (s[i] !== ' '){ //if the current character is not a space
      spaceCounter = 0;
      nonSpaceCounter ++;
    }

  }
  return true;
}
```

4. `Fake Binary`

```Javascript
function fakeBin(x){
  let result = '';
  for(let i = 0; i < x.length; i++){
    if(parseInt(x[i]) < 5){
      result += '0';
    }
    else{
      result += '1';
    }
  }
  return result;
}
```

## Thursday
1. `Remove All Exclamation Marks From The End Of Sentence`

```Javascript
function remove(str) {
  let newStr = '';
  for (let i = str.length - 1; i > 0; i--) {
    if (str[i] !== '!') {
      newStr = str.substring(0, i + 1);
      break;

    }
  }
  return newStr;
}
```

2. `Vowel Remover`

```Javascript
function shortcut (string) {
  let vowel = ['a', 'e', 'i', 'o', 'u'];
  let newStr = '';
  let found;
  for(let i = 0; i < string.length; i++){
    found = false;
    for(let j = 0; j < vowel.length; j++){
      if(string[i] === vowel[j]){t 
        found = true;
        break;
      } 
    }
    if(found === true) continue;
    newStr += string[i];
  }
  return newStr;
}
```

3. `Rock Paper Scissors!`

```Javascript
const rps = (p1, p2) => {
  if(p1 === 'scissors' && p2 === 'paper') return 'Player 1 won!';
  if(p1 === 'paper' && p2 === 'rock') return 'Player 1 won!';
  if(p1 === 'rock' && p2 === 'scissors') return 'Player 1 won!';
  if(p1 === p2) return 'Draw!';
  return 'Player 2 won!';
};
```

4. `Persistent Bugger`

```Javascript
function persistence(num) {
  let count = 0;
  let digit = [];
  while(num >= 10){
    digit = num.toString().split('');
    num = 1; 
    for(let i = 0; i < digit.length; i++){
      num *= digit[i];
    }
    count++;
  }
  return count;
} 
```

# Week 3 challenges

## Monday

1.`Who Likes It?`

```Javascript
function likes(names) {
  if (names.length == 0) return "no one likes this";
  if (names.length == 1) return `${names[0]} likes this`;
  if (names.length == 2) return `${names[0]} and ${names[1]} like this`;
  if (names.length == 3) return `${names[0]}, ${names[1]} and ${names[2]} like this`;
  return `${names[0]}, ${names[1]} and ${names.length - 2} others like this`;
}
```

2.`Bit Counting`

```Javascript
var countBits = function (n) {
  let binary = n.toString(2);
  return binary.split('').reduce(
    (previousValue, currentValue) => parseInt(previousValue) + parseInt(currentValue),0);
};
```

3.`Your order, please`

```Javascript
function order(words) {
  /*Get the number of the word*/
  let wordNumber = [];
  for (let i = 0; i < words.length; i++) {
      //if the value is a number
      if (!Number.isNaN(Number(words[i]))) wordNumber.push(words[i]);
  }

  /*Cleaning whitespaces values fromm wordNumber array*/
  let cleanWordNumber = [];
  for (let i = 0; i < wordNumber.length; i++) {
      if (wordNumber[i] != ' ') cleanWordNumber.push(wordNumber[i]);
  }

  /*Getting the result array*/
  let result = [];
  let wordsArray = words.split(' ');
  for (let i = 0; i < wordsArray.length; i++) {
      result[cleanWordNumber[i]] = wordsArray[i];
  }

  /*Cleaning the undefined values from result array*/
  let cleanresult = [];
  for (let i = 0; i < result.length; i++) {
      if (result[i] != undefined) cleanresult.push(result[i]);
  }
  //return the final string
  return cleanresult.join(' ');
}
```

## Tuesday

1.`Simple Pig Latin`
```Javascript
function pigIt(str) {
  let punctuaionMarks = ['!', '?', '.', ',', ':', ';'];
  let words = str.split(' ');
  let firstLetter = '';
  let restOfLetters = '';
  for (let i = 0; i < words.length; i++) {
    if (punctuaionMarks.indexOf(words[i]) >= 0) continue;
    firstLetter = words[i].slice(1);
    restOfLetters = words[i].slice(0,1);
    //replacing the word
    words[i] = firstLetter + restOfLetters + 'ay';
  }
  return words.join(' ');
}
```

2.`Counting Duplicates`
```Javascript
function duplicateCount(text){
  let result = 0;
  let count = 0;
  let chars = text.toLowerCase().split('').sort();
  let actualChar = chars[0];
  for(let i = 0; i <= chars.length; i++){
    if(actualChar !== chars[i]){
      actualChar = chars[i];
      if (count >= 2) result++;
      count = 0;
    }
    count++;
  }
  return result;
}
```

3.`Decode The Morse Code`
```Javascript
decodeMorse = function(morseCode){
  let letter = morseCode.trim().split(' ');
  let word = '';
  let spaceCount = 0;
  const result = letter.map((str) => {
    if(str !== '') word += MORSE_CODE[str];
    if(str === '') spaceCount++;
    if(spaceCount >= 2){
      spaceCount = 0;
      word += ' ';
    }
  });
  return word;
}
```

## Wednesday

1.`Valid Parentheses`
```Javascript
function validParentheses(parens) {
  let counter = 0;  //counter for the parentheses
  for (let i = 0; i < parens.length; i++) {
    if (parens[i] === '(') counter++;
    if (parens[i] === ')') counter--;
    //if there is more ')' than '('
    if (counter < 0) return false; 
  }
  //if there is the same amount of '(' as ')'
  //it will return true
  return counter === 0;
}
```

2.`Convert String To Camel Case`
```Javascript
function toCamelCase(str){
  for(let i = 0; i < str.length; i++){
    str = str.replace('-', ' ');
    str = str.replace('_', ' ');
  }
  str = str.split(' ');
  let result = str[0];
  let word = '';
  for(let i = 1; i < str.length; i++){
    word = str[i];
    result += word[0].toUpperCase() + word.slice(1).toLowerCase();
  }
  return result;
}
```

3.`Unique In Order`
```Javascript
var uniqueInOrder=function(iterable){
  let result = [];
  let value;  //using undefined to work with every kind of value
  for(let i = 0; i < iterable.length; i++){
    if(value !== iterable[i]){
      result.push(iterable[i]);
      value = iterable[i];
    }
  }
  return result;
}
```

## Thursday

2.`Encrypt This!`
```Javascript
var encryptThis = function(text) {
  let ascii;
  let secondLetter;
  let lastLetter;
  const result = text.split(' ').map((str) => {
    if (str.length === 1) return `${str.charCodeAt()}`;
    if (str.length === 2) return `${str[0].charCodeAt()}${str[1]}`;
    secondLetter = str[1];
    lastLetter = str[str.length - 1];
    ascii = str.charCodeAt(0);
    
    str = str.split('');
    str[0] = ascii;
    str[str.length-1] = secondLetter;
    str[1] = lastLetter;
    str= str.join('');
    return str;
  });
  return result.join(' ');
}
```

# Week 4 challenges

## Wedndesday

1.`Simple Validation Of A Username`
```Javascript
function validateUsr(username) {
    const res = /^[a-z0-9_]{4,16}$/.test(username);
    return res;
}
```

2.`Get Number From String`
```Javascript
function getNumberFromString(s) {
    return Number(s.replace(/\D/g, ''));
}
```

## Thursday

1.`String Cleaning`
```Javascript
function stringClean(s) {
    return s.replace(/[0-9]/g, '');
}
```

2.`Password Validation`
```Javascript
function validate(password) {
    return (
        /^[A-Za-z0-9]{6,}$/.test(password) &&
        /[A-Z]+/.test(password) &&
        /[a-z]+/.test(password) &&
        /[0-9]+/.test(password)
    );
}
```

# Week 5 challenges

## Monday

1.`Find The Missing Letter`
```Javascript
function findMissingLetter(array) {
    const missing = array
        .map((letter) => letter.charCodeAt())
        .find((code, i, charCodeArray) => {
            if (i === 0) return false;
            return code - 1 != charCodeArray[i - 1];
        });
    return String.fromCharCode(missing - 1);
}
```

2.`Reverse Or Rotate?`
```Javascript
function revrot(str, sz) {
    if (sz <= 0 || str === '' || sz > str.length) return '';
    //str.push(str.shift());
    let reg = new RegExp(`\\d{${sz}}`, 'g');
    let chunks = str.match(reg); //pedazos en base a sz
    let sum = 0;
    let chunkArray = [];
    let result = chunks.map((chunk) => {
        console.log(chunk);
        sum = chunk
            .split('')
            .map((digit) => Math.pow(+digit, 3))  // saca las potencias de cada pedazo
            .reduce((prev, curr) => prev + curr, 0); // suma las potencias de cada pedazo
        chunkArray = chunk.split(''); // se parte el arreglo en pedazos otra ves
        if (sum % 2 === 0) return chunkArray.reverse().join(''); // realizando una reversa
        return chunkArray.push(chunkArray.shift()), chunkArray.join(''); //creando nuevamente un string
    });
    return result.join(''); //regresando el array original a un string
}
```

## Tuesday

1.`TypeScript Object Type`
```TypeScript
export interface User {
    name: string;
    age: number;
    occupation: string;
}

export const users: User[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    }
];

export function logPerson(user: User) {
    console.log(` - ${user.name}, ${user.age}`);
}

console.log('Users:');
users.forEach(logPerson);
```

2.`TypeScript Unions`
```TypeScript
interface User {
    name: string;
    age: number;
    occupation: string;
}

interface Admin {
    name: string;
    age: number;
    role: string;
}

export type Person = User | Admin;

export const persons: Person[] /* <- Person[] */ = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(user: Person) {
    console.log(` - ${user.name}, ${user.age}`);
}

persons.forEach(logPerson);
```

## Thursday

1.`What's Your Posion?`
```Javascript
function find(rats) {
    return rats.reduce((prev, curr) => {
        return prev + Math.pow(2, curr);
    }, 0);
}
```

2.`Array.diff`
```Javascript
function array_diff(a, b) {
    return a.filter((value) => !b.includes(value));
}
```
