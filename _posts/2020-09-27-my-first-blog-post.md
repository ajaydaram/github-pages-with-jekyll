---
title: "Welcome to my blog"
date: 2019-01-20
---

# ECMA Script

It is a standard version of JavaScript ECMA script is another fancy name for JavaScript. ECMAScript 6 is the latest version and was released in 2015.

Some of the powerful features of ECMA script are

* Arrow functions
* Classes
* Modules
* Promises
* Generators
* let and const


## Differences between **var** and **let** and **const** keywords

Consider the following code 

```
var continent = “Asia”;
var continent = “Europe”;
console.log(continent); 
```
This will print *Europe* to the console. The second declaration over-ride the first value. In working with large applications it is possible to overwrite accidentally and will cause errors in the code. It is also not easy to fix the bugs. 

*ES6* introduced the new keyword *let* in the variable declarations. 

```
let continent = “ Asia “ 
let continent = “ Europe “ 
Console.log(continent):

``` 
The above code will throw the error. The important difference is you can name it only once and the declaration is locked. 

```
let dogName;
let quote;
function dogTalk() {
  “Use strict”;
  
  dogName = “scobby”;
  quote = dogName + “ says Bow Bow!”;
  
  }
   dogTalk()
```

## Scoping 

Scope of the declared variable is one of the key feature to note down while declaring the variable with *let* or with *var* 

### Declaring variable with *var* keyword

With **var** the variable is declared globally. inside a **function** it has only local scope. 


```
var arrayContainingNumbers = [];
for (var i = 0; i < 3; i++) {
 arrayContainingNumbers.push(i);
}
 console.log(arrayContainingNumbers);
 // returns [0, 1, 2]
 console.log(i);
 //returns 3
 
 ```
 
 
 
 To understand the concept of scoping, it is better to understand how JavaScript works. We see that with the keyword **var**, *i* is declared globally. At the beginning i is initialised to 0 and then updates to 3. 
 
 The above code can also is same as the below code: 
 

```
var arrayContainingNumbers = [];
var i;

for (i = 0; i < 3; i++) {
 arrayContainingNumbers.push(i);
}
 console.log(arrayContainingNumbers);
 // returns [0, 1, 2]
 console.log(i);
 //returns 3
 ``` 
 
 In both cases the variable with the name *i* updated to 3 and through out the entire programme it will remain 3. If you want to create to create a function and store it for later use inside for loop that have same *i* variable will cause unexpected behaviour or error. The reason is because of the updated global *i* variable.
 
 
 ``` 
 var updateNumberTwo;
   for (var i = 0; i < 3; i++ ) {
     If (i === 2) {
     UpdateNumberTwo = function() {
        return i ;
    };
   }
  }
    console.log(updateNumberTwo());
    //returns 3
    
     
    ``` 
    The result is 3 not 2 because the value assigned **i**  was updated and returns the global value of the **i** next we will see that the *let* keyword doesn’t follow this behaviour. 

### Declaring variable with *let* keyword

``` 
‘use strict’
 let updateNumberTwo;
   for (let i = 0; i < 3; i++ ) {
     If (i === 2) {
     UpdateNumberTwo = function() {
        return i ;
    };
   }
  }
    console.log(updateNumberTwo());
    //returns 3
     
```


   You can see that *i* is not defined as it was not declared in the global scope. It declared inside the for loop only. And also the console prints the updateNumberTwo is “2” as (0, 1, 2) created by the let keyword. 
   
   
### Declaring variable with *const* keyword 

ES6 also introduced **const** to declare variables. It works similarly like **let** and has a added functionality. This functionality makes it read only. It means that once a variable is assigned with **const**, it cannot be reassigned. 


```
“use strict”
const studentName = “John Doe”
 studentName = “Alice” //returns error
```
Unless you specifically know that the value of the variable doesn’t change avoids using constant. 
