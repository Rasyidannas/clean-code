# Assigning Good Names
Good names should be meaningful

## Why Name Matter
Well-named "Things" allow readers to understand your code without going through it in detail (class or function definitions and all other code).  
**Example:**  
1. `const user = new User()`  
2. `database.insert(user)`  
3. `if (isLoggedIn) {...}`  

## How to Name Things Correctly
### Variables & Constants
Here we can use all data containers, e.g. user input data, validation results, and a list of products. Use **nouns** or short phrases with **adjectives**.  
**Example:**  
1. `const userData = {...}`  
2.  `const isValid = ...`  
### Functions/Methods
Here we can use it for commands or calculated values, e.g. send data to server. check if user input is valid. Use **verbs** or short phrases with **adjectives**.  
**Example:**  
1. `sendData()`  
2. `inputIsValid()`  
### Classes
Here create "things", e.g. a user, a product, and an HTTP request body. Use **nouns** or short phrases with **nouns**.  
**Example:**  
1. `class User {...}`  
2. `class RequestBody {...}`  

## Kind of Name Casing
This is styling writing standard conventions for naming variables, functions, classes, and other elements in code.
1. snake_case | `is_valid`, `send_response`
2. camelCase  | `isValid`, `sendResponse`
3. PascalCase | `AdminRole`, `UserRepository`
4. kebab-case | `<side-drawer>`

## Naming Variables, Constants & Properties
1. For value is an **Object**,
    * describe the value, e.g. `user`, `database`
    * Provided more details without introducing redundancy, e.g. `authenticatedUser`, `sqlDatabase`
2. For value is a **Number** or **String**,
    * describe the value, e.g. `name`, `age`
    * Provided more details without introducing redundancy, e.g. `firstName`, `age`
3. For value is a **Boolean**,
    * answer a true/false question, e.g. `isActive`, `loggedIn`
    * Provided more details without introducing redundancy, e.g. `isActiveUser`, `userLoggedIn`
