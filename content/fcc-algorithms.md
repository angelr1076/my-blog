---
title: FreeCodeCamp Algorithm Challenges
url: /fcc-algorithms
date: "2018-12-24"
description: "I'm covering two of FCC's basic algorithms for beginners."
image: "img/unsplash-photos-5mZ_M06Fc9g.jpg"
credit: ""
thumbnail: ""
categories: [
    "JavaScript",
    "freeCodeCamp",
    "Beginner",
    "Algorithms",
]
---
## JavaScript Algorithms

Today, we’re going to cover several of freeCodeCamp’s algorithm challenges from the Javascript Algorithms And Data Structures Certification. I’ll skip the first “Celsius to Fahrenheit” challenge. I just feel like there’s not much to explain there where you can find the conversion pretty much anywhere on the internet. 

## Reverse a String

Let’s start with the “Reverse the String” challenge. The first time I solved this challenge, I used a few JavaScript built-in functions and chained them together like so:

 <dd> return str.split(‘’).reverse().join(‘’); </dd> 

I wanted to figure out another way of solving this aside from the more common route. I know FCC’s challenges are written in ES5, but I want to stay up to date and write all functions in ES6. At the end, I’ll print both the ES5 and ES6 functions.

This one’s fairly simple. We start off with a function:

<dd>reverseString = str => {</dd>
   <dd>return str;</dd>
<dd>}</dd>

<dd>reverseString(“hello");</dd>

We have our return statement inside the function, which we will later need to adjust to fit the variable we created. Outside of the function, we have our test function call. We can add a few more once we complete this just to be sure the function works as it is intended to. 

Next, we’ll add a variable inside of our function, an empty string, to store our new string. We’ll call it “newString”. We’ll use the “let” keyword since we’re declaring the variable but also reassigning it with each iteration of our for loop. I’m assuming you understand that JavaScript variables are written in camel case as well. 

<dd>reverseString = str => {</dd>
   <dd>let newString = “”;</dd>

   <dd>return str;</dd>
<dd>}</dd>

<dd>reverseString(“hello”);</dd>

Once the variable has been declared, we’ll create our for loop. A for loop consists of three statements: initial expression; condition; increment expression; All in that exact order. 

<dd>reverseString = str => {</dd>
   <dd>let newString = “”;</dd>
   
<dd>reverseString = str => {</dd>
  <dd>const newString = "";</dd>
  
  <dd>for (let i = str.length -1; i >= 0 ; i- -;) {</dd>

 <dd>}</dd>

  <dd>return str;</dd>
<dd>}</dd>

<dd>reverseString(“hello");</dd>

This is a little different than your typical for loop. If you’re fairly new to JavaScript, the (let i = str.length -1;) variable declaration might look a little off to you. What we’re trying to do here, with the -1, is start at the end of the string. You’ll see this at times when you’re trying to start at the end of the array, instead of 0 (beginning index of an array) you’ll declare a -1 which starts us off at the end. Next, we’ll tell the function that the index or i >= 0; that way, when the loop runs its course, it stops at the 0 index instead of continuing past our declaration. Finally, since we’re starting at the end of the string, we want to decrement our index count till we hit 0 so we’ll adjust our increment expression (in this case our decrement expression) to i- -;

Something you’ll want to do when testing your function is use your console.log() statement often. This helps you to better see what’s going on as you progress. We can add a console log to the for loop inside the block. 
   
<dd>reverseString = str => {</dd>
  <dd>let newString = "";</dd>
  
  <dd>for (let i = str.length -1; i >= 0 ; i- -;) {</dd>
  <dd>console.log(str[i]);</dd>
 <dd>}<dd>

  <dd>return str;</dd>
<dd>}</dd>

<dd>reverseString(“hello”);</dd>
<dd>reverseString(“Howdy”);</dd>

<dd>“o”</dd>
<dd>“l”</dd>
<dd>“l”</dd>
<dd>“e”</dd>
<dd>‘h”</dd>

<dd>“y”</dd>
<dd>“d”</dd>
<dd>“w”</dd>
<dd>“o”</dd>
<dd>“H”</dd>

By console logging str[i], we’re taking each iteration of the for loop running through each string. In this case, we know our function works because both strings have been reversed. We just need to add our statement inside the for loop to tell the loop what to do. Let's add “newString += str[i]” inside the for loop. This is the same as declaring, “newString = newString + str[i]”, but it’s just a shorthand version of the same statement. So now, our empty string variable is now equal to the “str” argument passed into the function. Let’s also change our return statement to return the newString variable, too!


<dd>reverseString = str => {</dd>
  <dd>let newString = "";</dd>
  
  <dd>for (let i = str.length -1; i >= 0 ; i- -) {</dd>
    <dd>newString += str[i];</dd>
  <dd>}</dd>

  <dd>return newString;</dd>
<dd>}</dd>

<dd>reverseString("hello");</dd>
<dd>reverseString("Howdy";</dd>

Finally, we have our reverseString function working. It can also be written in ES5 to pass the FCC test. 

<dd>function reverseString (str) {</dd>
   <dd>let newString = "";</dd>
  
  <dd>for (let i = str.length -1; i >= 0 ; i- -) {</dd>
    <dd>newString += str[i];</dd>
  <dd>}</dd>

  <dd>return newString;</dd>
<dd>}</dd>


## Factorialize a Number

This description is taken verbatim from the FCC challenge:

“Return the factorial of the provided integer.
If the integer is represented with the letter n, a factorial is the product of all positive integers less than or equal to n.
Factorials are often represented with the shorthand notation n!
For example: 5! = 1 * 2 * 3 * 4 * 5 = 120
Only integers greater than or equal to zero will be supplied to the function.”

This algorithm is pretty straight forward. Let’s rule out any number 0 or below since the lowest factorial we will ever use is 1. 

<dd>factorialize = num => {
  <dd>if (num <= 0) {
    <dd>return 1;
  <dd>}
<dd>}

<dd>factorialize(5);

What we’re doing here is creating a safeguard against an argument 0 or below. If this happens, let’s convert the number to 1 and run the function. When that happens, the return is 1. All we have to do now is return our execution sequence. We’ll do that below:

<dd>factorialize = num => {</dd>
  <dd>if (num <= 0 ) {</dd>
    <dd>return 1;</dd>
  <dd>}</dd>
  <dd>return num * factorialize(num -1);</dd>
<dd>}</dd>
<dd>factorialize(5);</dd>

What we did here is take the argument passed, let’s say 5, and used recursion (calling a function inside a function, or in this example, a function calling itself). So we’ll take 5 x (5-1) or, 
5 x (4) until we get to the number 1. (5 * (4 * (3 * (2 * (1)))). 

Written in ES5 we have:
<dd>function factorialize (num) {</dd>
  <dd>if (num <=0 ) {</dd>
    <dd>return 1;</dd>
  <dd>}</dd>
  <dd>return num * factorialize(num -1);</dd>
<dd>}</dd>

<dd>factorialize(5); // 120</dd>

These aren’t complex algorithms at all, but when you’re beginning to work with JavaScript, especially at the time when the FCC modules stop the handholding, these can seem very confusing so I wanted to add my solutions and explanation of each process and hope that I can help a few people out in the process. I’ll be posting solutions each week on my blog if you’d like to visit me at angelroddy.com. You can also view my portfolio at angelroddie.com. Thanks for checking out my post!

Read next: [My Journey](/my-journey/).
