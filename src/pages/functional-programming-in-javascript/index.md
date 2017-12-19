---
title: Javascript functional programming basic examples
date: "2017-10-16T19:37:09:37.145Z"
tags: ["Javascript", "Functional Programming"]
---


**Functional programming**: programming paradigm. The output value of a function depends only on the arguments that are passed to the function, so calling a function f twice with the same value for an argument x produces the same result f(x) each time. This is in contrast to procedures depending on a local or global state, which may produce different results at different times when called with the same arguments but a different program state. Eliminating side effects, i.e., changes in state that do not depend on the function inputs, can make it much easier to understand and predict the behavior of a program, which is one of the key motivations for the development of functional programming.

**High-order-functions**: Functions that operate on other functions, either by taking them as arguments or by returning them.


**filter():**
```javascript
var animals = [
    { name: 'John', species: 'dog' },
    { name: 'Jane', species: 'cat' },
    { name: 'James', species: 'frog' },
    { name: 'Joe', species: 'horse' },
];

// With a for loop:
var dogs = [];
for (var i=0; i<= animals.length; i++) {
    if( animals[i].species === 'dog') 
        dogs.push(animals[i]);
}

// Functional:
var dogs = animals.filter(function(animal) {
    return animal.species === 'dog';
};

// Another way, decoupling:
var isDog = function(animal) {
    return animal.species ==='dog';
}
var dogs = animals.filter(isDog);

```


**map():**
```javascript
var animals = [
    { name: 'John', species: 'dog' },
    { name: 'Jane', species: 'cat' },
    { name: 'James', species: 'frog' },
    { name: 'Joe', species: 'horse' },
];

// With for loop:
var names = [];
for (var i=0; i<= animals.length; i++) {
    if ( animals[i]-species === 'dog') 
        names.push(animals[i].name);
}

// Functional:
var names = animals.map(function(animal) {
    return animal.name + ' is a ' + animal.species;
});

// Which using ES6 arrow functions can be:
var names = animals.map((animal) =>  { animal.name });
```

**reduce():**
```javascript
var orders = [
    { amount: 250 },
    { amount: 400 },
    { amount: 100 },
    { amount: 350 },
];

// For loop:
var  totalAmount = 0;
for (var i=0; i < orders.length; i++) {
    totalAmount += orders[i].amount;
}

// Functional:
var totalAmount = orders.reduce(function(sum, order) {
    return sum + order.amount;
}, 0);

// Which using ES6 arrow functions can be:
var totalAmount = orders.reduce(sum, order) => sum + order.amount, 0);

console.log(totalAmount);
```