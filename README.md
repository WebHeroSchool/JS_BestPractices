# Introduction
This guide serves as the set of best standards and practices that outline how Javascript code should be written and organized.

## 1. Naming Convention
Avoid single letter names. Be descriptive with your naming, use intention-revealing names.  Use camelCase when naming objects, functions, and instances.

✅
``` js
  const thisIsMyObject = {};
  function thisIsMyFunction() {}
  function count () {}
  let firstName, lastName
  let counter
```
❌

``` js
  const o = {};
  const this_is_my_object = {};
  function c() {}
  let fName, lName
  let cntr
```

## 2. Statement Rules
Every statement must be terminated with a semicolon.

✅
``` js
  let person = {
    firstName: "John",
    lastName: "Doe",
    age: 35,
    eyeColor: "blue"
  };

  let animals = ["cat", "dog", "fox"];
```
❌
``` js
    let person = {
    firstName: "John",
    lastName: "Doe",
    age: 35,
    eyeColor: "blue"
  }

  let animals = ["cat", "dog", "fox"]
```


## 3. Declaring variables
Always use **const** or **let** to declare variables. Use **const** by default, unless a variable needs to be reassigned. The **var** keyword must not be used.

✅
```js
  const x = 2;
  const array = [1, 2, 3];
  let userName = 'Oksana';
```
❌
```js
  var x = 2;
  userName = 'Oksana';
  let sportTeam;
```

## 4. Arrow Functions
Arrow functions are preferred because they allow us to write shorter function syntax.
✅
```js
  hello = () => {
  return "Hello World!";
  }

  (a, b) => a + b + 100;
```
❌
```js
  // Traditional Function
  function (a, b){
    return a + b + 100;
  }

```

## 5. Explicit Comparators

Use explicit comparators === over coerced comparators ==.
It forces a pure comparison of explicit values with no coercion.

✅
```js
  "hello" === 1 //false
  2 === "2" //false
```
❌
```js
  "hello" == 1  //true
  "" == 0 //true
  2 == "2" // true
```


## 6.  Strings
Use single quotes '' for strings.
If a string contains a single quote character, consider using a template string to avoid having to escape the quote.
✅
```js
  let saying = `Say it ain't so`;
  let phrase = 'We are the so-called "Vikings" from the north.';
```
❌
```js
  let saying = 'Say it ain't so';
  let phrase = "We are the so-called "Vikings" from the north.";
```

Use template literals (delimited with `) over complex string concatenation. Template literals may span multiple lines.

✅
```js
  function sayHi(name) {
    return `How are you, ${name}?`;
  }
```
❌
```js
  function sayHi(name) {
    return 'How are you, ' + name + '?';
  }
```

## 7. Nesting Levels
Try to avoid nesting code too many levels deep. Nesting too far can make your code super unreadable.

✅
```js
  for (let i = 0; i < 10; i++) {
    if (!cond) continue;
    // <- no extra nesting level
  }

```
❌
```js
  for (let i = 0; i < 10; i++) {
    if (cond) {
    // <- one more nesting level
    }
  }

  firstFunction(args, function() {
    secondFunction(args, function() {
      thirdFunction(args, function() {
          // And so on…
      });
    });
  });
```

## 8. Defining functions
Where possible, use the function declaration to define functions over function expressions:

✅
```js
  function sum(a, b) {
    return a + b;
  }
```
❌
```js
  let sum = function(a, b) {
    return a + b;
  }
```

## 9. Conditionals
When using for/for...of loops, make sure to define the initializer properly, with a let keyword:

✅
```js
  let cats = ['Athena', 'Luna'];
  for(let i of cats) {
    console.log(i);
  }
```
❌
```js
  let cats = ['Athena', 'Luna'];
  for(i of cats) {
    console.log(i);
  }
```

## 10. Switch statements
It’s a good practice to end your switch statements with a default.

✅
```js
  let fruit = 'Papayas';
  switch(fruit) {
    case 'Oranges':
      console.log('Oranges are $0.59 a pound.');
      break;
    case 'Papayas':
      console.log('Mangoes and papayas are $2.79 a pound.');
      break;
    default:
      console.log(`Sorry, we are out of ${fruit}`);
  }
```
❌
```js
  let fruit = 'Papayas';
  switch(fruit) {
    case 'Oranges':
      console.log('Oranges are $0.59 a pound.');
      break;
    case 'Papayas':
      console.log('Mangoes and papayas are $2.79 a pound.');
      break;
  }
```
