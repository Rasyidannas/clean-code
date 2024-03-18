# Function & Methods
## What Makes Up a Function?
1. Working with the function should be easy/readable, _because the length of the function body matters_
   * Function body should be small (try splitting it into multiple functions)
   * Functions should do exactly one thing
   * Functions should do work that's one level of abstraction below their name `emailIsValid` _this should return true/false of validating email address_
2. Calling the function should be readable, _because the number and order of arguments matter_
   * Minimize the number of parameters (2 or 3 parameters are fine to read/readable if you want to have more you can save it in an object, array etc )
   * Try to avoid output arguments - especially if they are unexpected
3. DRY (Don't Repeat Yourself), _Don't write the same code more than once(reuseable function written/exist)_
4. Keep try function pure
5. Avoiding unexpected side effect
## Example Good Function
1. Exercise One
```Javascript
function createUser(email, password) {
  try {
    setupUser(email, password);
  } catch (error) {
    handleError(error);
  }
}

function setupUser(email, password) {
  validateUserData(email, password);

  const user = buildUser(email, password);

  saveUserToDatabase(user);
}

function validateUserData(email, password) {
  if (!userDataIsValid(email, password)) {
    throw new Error('Invalid input!');
  }
}

function userDataIsValid(email, password) {
  return emailIsValid(email) && passwordIsValid(password);
}

function emailIsValid(email) {
  return email && email.includes('@');
}

function passwordIsValid(password) {
  return password && password.trim() !== '';
}

function buildUser(email, password) {
  return {
    email: email,
    password: password,
  };
}

function saveUserToDatabase(user) {
  database.insert(user);
}

function handleError(error) {
  console.log(error.message);
}
```
2. Exercise two
```Javascript
function initApp() {
  try {
    connectDatabase();
  } catch (error) {
    console.log(error.message);
    // showErrorMessage(...)
  }
}

function connectDatabase() {
  const didConnect = database.connect();
  if (!didConnect) {
    throw new Error('Could not connect!');
  }
}

function determineSupportAgent(ticket) {
  if (ticket.requestType === 'unknown') {
    return findStandardAgent();
  }
  return findAgentByRequestType(ticket.requestType);
}

function isValid(email, password) {
  return email.includes('@') && password.length >= 7;
}
```
