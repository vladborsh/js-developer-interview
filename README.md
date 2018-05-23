# Cracking JS Developer (Angular) interview

## Getting Started

This guide gives you a few tips on learning and education. Read the question, google, go to the next, repeat. There are no guarantees that you will receive the same questions in your interview. But I hope that this list will simplify it.

## Table of contents

* [Javascript](https://github.com/vladborsh/js-developer-interview#javascript)
* [Typescript](https://github.com/vladborsh/js-developer-interview#typescript)
* [Angular](https://github.com/vladborsh/js-developer-interview#angular)
* [Exercises](https://github.com/vladborsh/js-developer-interview#exercises)
* [Links](https://github.com/vladborsh/js-developer-interview#links)

## Interview questions

### Javascript

#### Type conversion

* What javascript types do you know?
* What types of conversion do you know?
* How works ``` Object + number```?
* How works ``` undefined + string```?
* How works ``` if (new Boolean(false))```?
* How works ``` if ( { a: 4 } )```?
* How convert number to string?

#### Event 

* What event stages do you know?
* What is target?
* ``` stopPropagation``` vs ```stopImmediatePropagation``` differences
* How throw event?
* How catch event?
* How catch event on capturing stage?
* How change colors on multiple divs on mouse click? WHat is delegation? 

#### OOP in javascript

* How wroks pototype inheritance?
* What is ```__proto__``` propetry and how we get it? Why we havn't write new properties to ```__proto__``` directly?
* How we make prototype inheritance in javascript?
* What we get in instance of B class (extends A class) if we will change some variable in A.prototype?
* What we get in instance of B class (extends A class) if we will change some variable that related to A class?
* (Bonus) Make polyfill for ```Object.create()```

#### Context

* What way to pass the context in funciton do you know?
* In which stage function get the context variable "this"?
* What is lexical environment?
* (Bonus) Make polyfill for ```bind()```

#### Closures

* What is closure? some examples...
* How implement conter with closure?
* How implement module with closure?
* How save context with closure? (bonus for setTimeout example)

#### Promises

* What stages of promise do you know?
* How chain promise?
* What returns onFullfiled function?
* What returns catch if we chain it to promise invocation?
* How works finally?
* (Bonus) make polyfill for ```Promise.all```

### Typescript

* Why we have to use let and const instead of var?
* Why we have to use arrow functions?
* What interfaces are compiled into?
* What are the decorators under the hood?
* How create own decorator?

### Angular

#### Components

* How componennts can communicate with each other?
* Components lifecycle hooks order
* How works view encapsulation? What types of view encapsulation do you know?
* How we can detect click on component?
* What is host listener and host binding?
* (Bonus) Ways to change child components styles

#### Change detenction

* What is zones? How it works?
* How works change detection in angular?
* What approaches do you know to disable change detection in components?
* What approaches do you know to enable change detection in components again? 
* (Bonus) How it works?

#### RxJS

* What is cold and hot observables?
* What are the differences between the subject and the observable?
* Subject types?
* What operator on observable do you know?
* ```flatMap``` and ```map``` differences?
* ```flatMap``` and ```switchMap``` differences?
* Ways to unsubcribe of observable? 
* (Bonus) How works takeWhile and takeUntil?

#### DI & Modules

* How define new service and pass it to component?
* What in dependency injection and dependency tree?
* How works providers on module and providers on compoennts?
* How we can prevent injector creation for lazyloaded module?
* (Bonus) How implement ```forRoot``` method and why we need it?
* How implement lazyloading?

#### Pipes

* Why we need pipes?
* How implement custom pipe?
* What is pure and impure pipes?
* (Bonus) How implement statefull pipe?

#### Forms

* How implement template driven forms?
* How implement reactive forms?
* How create custom validator?
* How create dependent (from other control) custom validator?

#### Routing

* What is routing outlet?
* Why we need child routes?
* Why we need active route?
* Why we need guards and how implement custom guard?

### Testing

* How test component?
* What is ```TestBed```?
* How mock http service and test it?
* What is spy?

### Exercises

* Sort words by number inside: ```'ads2aa 5qw asd1aa' => 'asd1aa ads2aa 5qw'```
``` javascript
function sortWords(str) {
  var arr = str.split(' ');
  return arr.sort( (a,b) => {
    var num1 = +a.replace(/[^0-9]/g, '')
    var num2 = +b.replace(/[^0-9]/g, '')
    return num1-num2
  }).join(' ')
}
```

* Find and collect anagramms: ```['adsaa', 'asaad', 'gqw', 'qwg'] => [ [ 'adsaa', 'asaad' ], [ 'gqw', 'qwg' ] ]```
``` javascript
function sortWords(str) {
  var arr = str.split(' ');
  return arr.sort( (a,b) => {
    var num1 = +a.replace(/[^0-9]/g, '')
    var num2 = +b.replace(/[^0-9]/g, '')
    return num1-num2
  }).join(' ')
}
```

* Make funny object from string: ```'a.b.c.d' => { a : { b : { c : { d: null } } } } ```
``` javascript
function objectizer(str) {
  return str.split('.').reduceRight( (total, a) => {
    return { [a]: total }
  }, null);
}
```

* fibonacci
``` javascript
function fibo(num) {
  function fibo_run(prev, next, count) {
    return count > 0 ? fibo(next, prev+next, --count) : next;
  }
  return fibo_run(1, 1, num);
}
```


* Find monotone sequence: ```
  [2,3,4] => true;
  [4,3,1,1] => true;
  [2,5,1] => false;
  [1,2,3,0] => false;
  [1,2,2,2,1] => false```
``` javascript
function mono(arr) {
  var status;
  var prevStatus;
  for (var i = 0; i<arr.length-1; i++) {
    if (arr[i] == arr[i+1]) continue;
    if (prevStatus === undefined) {
      prevStatus = ((arr[i] - arr[i+1]) > 0)
      continue;
    }
    status = (arr[i] - arr[i+1] > 0)
    if (prevStatus == status) {
      continue;
    } else {
      return false;
    }
  }
  return true;
}
```

* Validate brackets: ```
  '()()()' => true;
  '(())()' => true;
  ')()' => false;
  '(()' => false;```
``` javascript
function bracketsValidate(str) {
  var counter = 0;
  for ( var i = 0; i < arr.length; i++) {
    if ( arr[i] == ')' ) counter--;
    if ( arr[i] == '(' ) counter++;
    if ( counter < 0) return false;
  }
  return counter == 0;
}
```

* Compress word: ```'aaavvdeeemmmg' => 'a3v2de3m3g'```
``` javascript
function compressWord(str) {
  var result = '';
  var counter = 1;
  for ( var i = 0; i < str.length; i++) {
    if (result.length == 0) {
      result = result.concat(str[i])
      continue;
    }
    if (result[result.length-1] != str[i]) {
      if (counter > 1) {
        result = result.concat(counter)
        counter = 1;
      }
      result = result.concat(str[i])
    } else {
      counter++;
    }
  }
  return result;
}
```

* Currying: ```add(4)(3)(1) => 8```
``` javascript
function add(a) {
  function addFunc(b) {
    a += b;
    return addFunc;
  }
  addFunc.valueOf = function() {
    return a;
  }
  addFunc.toString = function() {
    return a;
  }
  return addFunc
}
```

* Create increment function for array (behave like number): ```
  [4,5,3].increment() => [4, 5, 4];
  [4,5,9].increment() => [4, 6, 0]```
``` javascript
Array.prototype.increment = function() { 
  var incremented = false; 
  this.reverse().forEach( (item,i) => { 
    if ( item < 9 && !incremented ) { 
      this[i] = ++item; incremented = true; 
    } else if (item == 9) {
      this[i] = 0;
    }
  } ); 
  return this.reverse().slice()  
}
```

## Links

* [Javascript.info](https://javascript.info/first-steps) - From the basics to advanced topics with simple, but detailed explanations
* [JavaScript Design Patterns](https://addyosmani.com/resources/essentialjsdesignpatterns/book/) - This book is targeted at professional developers wishing to improve their knowledge of design patterns and how they can be applied to the JavaScript programming language.
* [Rangle's Angular Training Book](https://angular-2-training-book.rangle.io/handout/why_angular_2.html) - This book will cover the most important Angular topics