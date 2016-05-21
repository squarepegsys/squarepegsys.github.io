count: false

## Test-Driven Development with Spock

### Mike Hostetler

![Spock](img/spock.gif)
---

## About Me

I work for ![OPI](img/2015-OPI-Logo-Stacked.gif)

I code in : Java, Groovy, Python (in any order)

Also a board game nerd .

#### Contact me!

 <i class="fa fa-github"></i>  https://github.com/squarepegsys/

 <i class="fa fa-twitter"></i> https://twitter.com/mikehoss42

 <i class="fa fa-rss"></i> http://mike.hostetlerhome.com

---

## Spock

* Test Framework for Java and Groovy
* Standard test framework for Grails
* Easy to make data-driven tests
* Easy to Mock collaborators
* Uses JUnit, so runs everywhere

---

## Kata-Style


We are going to do the String Calculator kata, based on:
http://osherove.com/tdd-kata-1/

(Read: shamelessly stolen)

---
## Introduction

* Try not to read ahead.
* Do one task at a time. The trick is to learn to work incrementally.
* Make sure you only test for correct inputs. there is no need to test for invalid inputs for this kata
* No refactoring anything until all existing tests pass.
---

## Step 1

* Create a simple String calculator with a method int Add(string numbers)
    1. The method can take 0, 1 or 2 numbers, and will return their sum (for an empty string it will return 0) for example `“”` or `“1”` or `“1,2”`
    2. Start with the simplest test case of an empty string and move to 1 and two numbers
    3. Remember to solve things as simply as possible so that you force yourself to write tests you did not think about
    4. Remember to refactor after each passing test
---

## Step 2

* Allow the Add method to handle an unknown amount of numbers

---

## Step 3

* Allow the Add method to handle new lines between numbers (instead of commas).
   1. the following input is ok:  `1\n2,3`  (will equal 6)
   2. the following input is NOT ok:  `1,\n` (not need to prove it - just clarifying)

---

## Step 4

* Support different delimiters
   1. to change a delimiter, the beginning of the string will contain a separate line that looks like this:   `//[delimiter]\n[numbers…]` for example `//;\n1;2` should return three where the default delimiter is `;` .
   2. the first line is optional. all existing scenarios should still be supported

---

## Step 5

* Calling Add with a negative number will throw an exception “negatives not allowed” - and the negative that was passed. Ff there are multiple negatives, show all of them in the exception message

---

## Mocks
![mock](img/mock.gif)
