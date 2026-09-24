MODULE 05 — ASSIGNMENT  
Problem Solving with AI (Claude Code + JavaScript)  
Name: MD Jobael Haque (Arif) ID: 01675979838 Batch: 21  
Course: AI Driven SQA — Manual & Automation Testing \| OSTAD

## Q1. JavaScript Coding Practice

The five programs below solve common problem-solving exercises in
JavaScript. Each includes a problem statement, source code, sample
input, expected output, a real execution screenshot, and a short
explanation.

## 1. Convert Celsius to Fahrenheit

## Problem Statement

Write a function that takes a temperature in Celsius and converts it to
Fahrenheit using the formula: F = (C × 9/5) + 32.

## Source Code

    function celsiusToFahrenheit(celsius) {
      return (celsius * 9 / 5) + 32;
    }

    console.log(celsiusToFahrenheit(25));

## Input

celsiusToFahrenheit(25)

## Expected Output

77

## Output

## Hands-on Practice

Executed live in VS Code to confirm the result independently.

## Explanation

The formula multiplies the Celsius value by 9/5 (which scales the
temperature to the Fahrenheit degree size) and then adds 32 (since the
two scales don't share a zero point). For 25°C: 25 × 9/5 = 45, then 45 +
32 = 77°F.

## 2. Find the Factorial of a Number

## Problem Statement

Write a function that calculates the factorial of a given non-negative
integer (e.g., 5! = 5 × 4 × 3 × 2 × 1 = 120).

## Source Code

    function factorial(n) {
      if (n === 0 || n === 1) return 1;
      let result = 1;
      for (let i = 2; i <= n; i++) {
        result *= i;
      }
      return result;
    }

    console.log(factorial(5));

## Input

factorial(5)

## Expected Output

120

## Output

## Hands-on Practice

Executed live in VS Code to confirm the result independently.

## Explanation

0! and 1! are defined as 1, so those are handled as a base case. For any
larger n, the loop multiplies result by every integer from 2 up to n.
For 5: 1 × 2 × 3 × 4 × 5 = 120

## 3. Check for Palindrome

## Problem Statement

Write a function that checks if a given word (e.g., "racecar") reads the
same backward as forward and returns true or false.

## Source Code

    function isPalindrome(word) {
      const cleaned = word.toLowerCase();
      const reversed = cleaned.split("").reverse().join("");
      return cleaned === reversed;
    }

    console.log(isPalindrome("racecar"));

## Input

isPalindrome("racecar")

## Expected Output

true

## Output

## Hands-on Practice

Executed live in VS Code to confirm the result independently.

## Explanation

Converting to lowercase first makes the check case-insensitive.
split("") turns the string into an array of characters, .reverse() flips
the order, and join("") puts it back together as a string. If the
reversed version matches the original exactly, the word is a palindrome
— "racecar" reversed is still "racecar", so the function returns true.

## 4. Sum of Array Elements

## Problem Statement

Write a function that takes an array of numbers and returns the sum of
all elements in the array.

## Source Code

    function sumArray(arr) {
      return arr.reduce((total, num) => total + num, 0);
    }

    console.log(sumArray([10, 20, 30, 40]));

## Input

sumArray(\[10, 20, 30, 40\])

## Expected Output

100

## Output

## Hands-on Practice

Executed live in VS Code to confirm the result independently.

## Explanation

reduce() walks through the array once, carrying a running total
(starting at 0) and adding each element to it in turn. For \[10, 20, 30,
40\], the total accumulates as 0 → 10 → 30 → 60 → 100.

## 5. FizzBuzz (Basic)

## Problem Statement

Write a loop from 1 to 15 that prints "Fizz" for numbers divisible by 3,
"Buzz" for numbers divisible by 5, "FizzBuzz" for numbers divisible by
both, and the number itself otherwise.

## Source Code

    for (let i = 1; i <= 15; i++) {
      if (i % 3 === 0 && i % 5 === 0) {
        console.log("FizzBuzz");
      } else if (i % 3 === 0) {
        console.log("Fizz");
      } else if (i % 5 === 0) {
        console.log("Buzz");
      } else {
        console.log(i);
      }
    }

## Input

Loop from 1 to 15 (no external input)

## Expected Output

1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz
Output

## Hands-on Practice

Executed live in VS Code to confirm the result independently.

## Explanation

The check for both 3 and 5 must come first, otherwise a multiple of 15
would only ever match the first true condition (3 or 5) and never reach
"FizzBuzz". Each number from 1 to 15 is tested in order: multiples of 15
print "FizzBuzz", other multiples of 3 print "Fizz", other multiples of
5 print "Buzz", and everything else prints the plain number.
