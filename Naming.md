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
1. For function performs on operation, so it describes the operation, e.g. `getUser(...)`, `response.send()`, `getUserByEmail(...)`
2. For function computes a Boolean, so it answers a true/false question, e.g. `isValid(...)`, `purchase.isPaid()`, `emailIsValid(...)`
#### Examples - Function / Method Names
1. What does the function do? Save user data to a database
   * Bad Names, e.g. `process(...)`, `handle(...)` _because are very unspecific - what is being "processed"?_
   * Okay Names, e.g. `save(...)`, `storeData(...)` _because at least we know that something is saved - but what?_
   * Good Names, e.g. `saveUser(...)`, `user.store(...)` _because the intent is very clear - especially with the method_
2. What does the function do? Validate the user input
   * Bad Names, `process(...)`, `save(...)` _because unspecific ("process") or even misleading ("save")_
   * Okay Names, `validateSave(...)`, `check(...)` _because both names are not 100% specific_
   * Good Name, e.g. `validate(...)`, `isValid(...)` _because both make sense depends on what the function does exactly_
### Naming Classes
1. Describe the Object, e.g. `User`, `Product`,  `Customer`, `Course` _Avoid redundant suffixes e.g. `DatabaseManager`_
#### Examples - Classes Names
1. What object is described? A User
   * Bad Names, e.g. `class UEntity`, `class ObjA` _because both are very unspecific_
   * Okay Names, e.g. `class UserObj`, `class AppUser` _because both class names have redundant information_
   * Good Names, e.g. `class User`, `class Admin` _because "User" is just fine - or "Admin" if it's a more specific kind of user_
2. What object is described? A Database (in code)
   * Bad Names, e.g. `class Data`, `class DataStorage` _because it's not clear that we're describing a database_
   * Okay Names, e.g. `class Db`, `class Data` _because not 100% specific_
   * Good Names, e.g. `class Database`, _because "Database" is good, "SQLDatabase" might be even better_

### Exercise Naming Variables, Function, and Classes
```Phyton 
from datetime import datetime


class BlogPost:
    def __init__(self, title, description, date_published):
        self.title = title
        self.description = description
        self.date_published = date_published

    def print(self):
        print('Title: ' + self.title)
        print('Description: ' + self.description)
        print('Published: ' + self.date_published)


title = 'Clean Code Is Great!'
description = 'Actually, writing Clean Code can be pretty fun. You\'ll see!'
now = datetime.now()
formatted_date = now.strftime('%Y-%m-%d %H:%M')

blog_post = BlogPost(title, description, formatted_date)
blog_post.print()
```

```Phyton 
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y


class Rectangle:
    def __init__(self, origin, width, height):
        self.origin = origin
        self.width = width
        self.height = height

    def get_area(self):
        return self.width * self.height

    def print_coordinates(self):
        top_right = self.origin.x + self.width
        bottom_left = self.origin.y + self.height
        print('Starting Point (X)): ' + str(self.origin.x))
        print('Starting Point (Y)): ' + str(self.origin.y))
        print('End Point X-Axis (Top Right): ' + str(top_right))
        print('End Point Y-Axis (Bottom Left): ' + str(bottom_left))


def build_rectangle():
    rectangle_origin = Point(50, 100)
    rectangle = Rectangle(rectangle_origin, 90, 10)

    return rectangle


rectangle = build_rectangle()

print(rectangle.getArea())
rectangle.print_coordinates()
```
