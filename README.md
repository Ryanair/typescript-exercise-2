# typescript-exercise-2
Workshop Typescript exercise on abstractions.

The main purpose of this exercise is to get familiar with Typescsript's
classes and interfaces.

## Required

For this exercise you need to have NodeJs

[NodeJS](https://nodejs.org/en/)

and also Typescript installed

```bash
$ npm i -g typescript
```

## Goal

The goal is to create a common class which will print out its inputs and outpus.

## Exercise 2

Create a class named LogService providing a public interface method, named log.

Log will accept any type of input and print it in stdout.

LogService should also provide a public interface named onDestroy which takes
only a string input and prints it out in stdout.

Create a class, named MyComponent, implementing 2 interfaces: OnInit, OnDestroy.

Your class must be placed in a file called my.component.ts (and also exported).

Interface OnInit should provide a
```
function named: ngOnInit
```

Interface OnDestroy should provide a
```
function named: ngOnDestroy
```

MyComponent class should also extend a class named CommonComponent which has a
```
public array property, named inputs, of type any
```

MyComponent class should also contain a
```
private counter, which will always provide the number of inputs which are of type: number
```
Counter value should only be set once, inside ngOnInit method.

MyComponent class should also provide the value of counter via a public getter method,
named getCounter. The getCounter should reply with the counter value.

MyComponent class should also contain a
```
private logSvc property of type LogService.
```
You must not instatiate LogService inside MyComponent class, so
can you think of a good place to assign a value to this property?

MyComponent should use LogService.log in ngOnInit, and LogService.onDestroy in ngOnDestroy.
On ngOnInit, it should log the inputs, and on onDestroy should log its class name.

Now, instantiate a new LogService object.
Instantiate a new MyComponent object and assign (inject) the previously instatiated LogService type object.
Assign to inputs property, the following
```
[1, '2', 'Name', -3]
```

Invoke the ngOnInit once and verify the output
```
[1, '2', 'Name', -3]
```

Invoke the following (assuming myObj is your MyComponent instance)
```ts
console.log(myObj.getCounter());
```
and verify the output
```
2
```

Invoke the ngOnDestroy and verify the output
```
MyComponent
```

## Guide

To compile and run your code

```bash
$ tsc my.component.ts && node my.component.js
```
