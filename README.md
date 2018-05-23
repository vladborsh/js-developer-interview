# Cracking JS Developer (Angular) interview for intermediate level

## Getting Started

This guide gives you a few tips on learning and education. Read the question, google, go to the next, repeat. There are no guarantees that you will receive the same questions in your interview. But I hope that this list will simplify it.

### Javascript

#### Type conversion

* What javascript types do you know?
* What types of conversion do you know?
* How works Object + number?
* How works undefined + string?
* How works if (new Boolean(false))?
* How works if ( { a: 4 } )?
* How convert number to string?

#### Event 

* What event stages do you know?
* What is target?
* stopPropagation() vs stopImmediatePropagation() differences
* How throw event?
* How catch event?
* How catch event on capturing stage?
* How change colors on multiple divs on mouse click? WHat is delegation? 

#### OOP in javascript

* How wroks pototype inheritance?
* What is "proto" propetry and how we get it? Why we havn't write new properties to "proto" directly?
* How we make prototype inheritance in javascript?
* Make polyfill for Object.create()
* What we get in instance of B class (extends A class) if we will change some variable in A.prototype?
* What we get in instance of B class (extends A class) if we will change some variable that related to A class?

#### Context

* What way to pass the context in funciton do you know?
* In which stage function get the context variable "this"?
* What is lexical environment?

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
* flatMap and map differences?
* flatMap and switchMap differences?
* Ways to unsubcribe of observable? 
* (Bonus) How works takeWhile and takeUntil?

#### DI & Modules

* How define new service and pass it to component?
* What in dependency injection and dependency tree?
* How works providers on module and providers on compoennts?
* How we can prevent injector creation for lazyloaded module?
* (Bonus) How implement forRoot method and why we need it?
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
* What is TestBed?
* How mock http service and test it?
* What is spy?

### Exercises
