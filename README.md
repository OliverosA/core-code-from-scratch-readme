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
      if(string[i] === vowel[j]){
        console.log(string[i]); 
        found = true;
        break;
      } 
    }
    if(found === true) continue;
    newStr += string[i];
    console.log('el valor nuevo es; ' + newStr);
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
