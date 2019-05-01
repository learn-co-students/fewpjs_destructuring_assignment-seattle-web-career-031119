# Destructuring Assignment

## Learning Goals

- Use destructuring to assign data to variables

## Introduction

As developers, sometimes we receive information in a collection like an
`Object` and we want to "pick and choose" elements out of the collection. It's
a major pain to extract each property / value pair out of an Object. Here
_destructuring_ can be a real help! Not only does destructuring help when
working with data in your application, it's essential for understanding how
to get JavaScript to include third-party code (like you find on [npm][]).

## Use Destructuring to Assign Data to Variables

In JavaScript, when we want to assign data to single variables from a top level
object such as this, we normally do it individually like so:

```js
const doggie = {
  first: 'Buzz',
  breed: 'Great Pyrenees',
  fur_color: 'black and white',
  activity_level: 'sloth-like',
  favorite_food: 'hot_dogs'
};
const first = doggie.first;  // Buzz
const breed = doggie.breed; // Great Pyrenees
```

This is pretty repetitive code, and it feels like there should be an easier way
to do this. With `destructuring`, there is! JavaScript gives us the ability to
assign multiple single variables at one time using a simple syntax.

```js

const doggie = {
  first: 'Buzz',
  breed: 'Great Pyrenees',
  fur_color: 'black and white',
  activity_level: 'sloth-like',
  favorite_food: 'hot_dogs'
};

const { first, breed } = doggie;
console.log(first);
console.log(breed);

```

We can also use it to destructure a nested syntax:
```js

const doggie = {
  first: 'Buzz',
  breed: 'Great Pyrenees',
  fur_color: 'black and white',
  activity_level: 'sloth-like',
  favorite_foods: {
    meats:{
      ham: 'smoked',
      hot_dog: 'oscar_meyer',
    },
    cheeses:{
      american: 'kraft'
    }
  }
};

const { ham, hot_dog } = doggie.favorite_foods.meats;
console.log(ham);
console.log(hot_dog);

```

### Destructuring Assignment with Arrays

Destructuring does not just work on objects - we can also use the same syntax
with `Array`s as well.

```js

const dogs = ['Great Pyrenees', 'Pug', 'Bull Mastiff']
const [medium, small, giant] = dogs
console.log(medium, small, giant) // Great Pyrenees, Pug, Bull Mastiff
```

The cool part is we can pick the parts of the `Array` that we want to assign!
```js

const dogs = ['Great Pyrenees', 'Pug', 'Bull Mastiff']
const [, small, giant] = dogs
console.log(small , giant) //  Pug, Bull Mastiff
```

### Destructuring Assignment with Strings

We can also destructure with strings, as a whole:

```js
const dogsName = 'Sir Woody BarksALot'
const [title, firstName, lastName] = 'Sir Woody BarksALot'.split(' ')
console.log(title, firstName, lastName) // Sir Woody BarksALot
```

And we can also destructure it in parts, just as we did with `Array`s above:

```js
const dogsName = 'Sir Woody BarksALot'
const [title, ,lastName] = 'Sir Woody BarksALot'.split(' ')
console.log(title, lastName) // Sir BarksALot
```

## Instructions

We are going to give you several `String`s, `Array`s, and `Object`s and you're
going to write several destructuring assignments for each. Write your code in
the `index.js` file. Let the instructions in the README and the tests guide you
through the process.

## Conclusion

"Destructuring assignment" is a fast, and efficient way to assign data to
variables from objects, `Array`s, and strings. It allows us to pick and choose the
pieces of data that we want to assign, and gives us lots of freedom to
manipulate the data as it is coming in. With practice, you'll be proficient at
it in no time.

## Resources

* [Destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

[npm]: https://www.npmjs.com/




Module 3 Solo Project Guidelines

You're going to be building a SPA or Single Page Application. Your frontend will be built with HTML, CSS, and JavaScript. You will also be tasked with first using a json-server with a db.json file as an MVP backend, before constructing your own backend API built with Ruby on Rails. The frontend application will communicate with the backend by making requests and receiving responses. This is a really exciting moment, the whole course up until this point is coming together!
Building out each feature you want for your application will be challenging, but you all are awesome and can do it. Remember to build iteratively and begin with a clear picture of an MVP.
Requirements
Do's
As a user of the application, I should be able to create, read, update, and delete the resource of your choosing. The Domain is up to you - some examples:
A photo sharing app
A ToDo List
A Craigslist-style app (users can perform CRUD actions on listings)
Use the json-server package to act as a backend. JSON Server allows you to create a json file to act like an API. Once you have your CRUD app working, you can create a Rails API and swap out the back end.
Your backend (first db.json and later Rails) will be the Single Source of Truth for your application. Your frontend will render the data it receives from the backend. The pattern will be that your frontend Fetches data from your server and then renders it. Then the user interacts with the data which may fire subsequent GET, POST or PATCH requests.
If your application requires a user model you can have users "sign in" or "sign up" by providing a username and/or email, but hold off on passwords for now.

Do Not's
Do not try to implement a user authentication system with passwords. When the page refreshes the current user will effectively be signed out. The way you learned this in the previous module relied on the fact that Rails was sending small pieces of data (cookies/sessions) back and forth along with every request and response. Now, we have two separate applications and need to use a slightly different pattern. We'll look at patterns for dealing with client-side auth later in the semester, so you'll have plenty of time to deal with this case.
