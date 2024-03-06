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

## Naming Variables, Functions, Class, and More
### Naming Variables, Constants & Properties Based Type Data
1. For value is an **Object**,
   * Describe the value, e.g. `user`, `database`
   * Provided more details without introducing redundancy, e.g. `authenticatedUser`, `sqlDatabase`
2. For value is a **Number** or **String**,
   * Describe the value, e.g. `name`, `age`
   * Provided more details without introducing redundancy, e.g. `firstName`, `age`
3. For value is a **Boolean**,
   * Answer a true/false question, e.g. `isActive`, `loggedIn`
   * Provided more details without introducing redundancy, e.g. `isActiveUser`, `userLoggedIn`
#### Example - Variables, Constants & Properties Names
1. What is stored? A user object (name, email, age)
   * Bad Names, e.g. `u`, `data` _because "u" and "data" could contain anything_
   * Okay Names, e.g. `userData`, `person` _because "userData" is a bit redundant, "person" is too unspecific_
   * Good Names, e.g. `user`, `customer` _because "user" is descriptive, "customer" is even more specific_
2. What is stored? User input validation result (true/false)
   * Bad Names, e.g. `v`, `val` _because "v" could be anything, "val" could also for "value"_
   * Okay Names, e.g. `correct`, `validatedInput` _because both terms don't necessarily imply a true/false value_
   * Good Names, e.g. `isValid`, `isCorrect` _because descriptive and value type is clear_
### Naming Function & Methods
1. Function performs on operation, so it describes the operation, e.g. `getUser(...)`, `response.send()`, `getUserByEmail(...)`
2. Function computes a Boolean, so it answers a true/false question, e.g. `isValid(...)`, `purchase.isPaid()`, `emailIsValid(...)`

