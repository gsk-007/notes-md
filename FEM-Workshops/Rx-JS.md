[Course Website](https://rxjs-fundamentals.netlify.app/)

> Think of RxJS as Lodash for events.

- A promise is an eventual value.
- An observable is a series of eventual values.

## Basic Observables Overview

  `of` : Create an observable out of one or more values.

```js
const example$ = of(1, 2, 3);
example$.subscribe(val => console.log(val));
```


`from` : Creates an observable from a promise or anything array- or observable-like

```js
const example$ = of([1, 2, 3]);
example$.subscribe(val => console.log(val));
```

### When to use *from* vs *of*

- Use from when whatever you're working with is kind of like an observable.
	- Arrays
	- Promises
	- Objects with a subscribe method
- Use of when it's nothing like an observable
	- Primitives: strings, numbers, Boolean , null, undefined
	- Objects 

### Syntax

```js
/* Depricated */
example$.subscribe(
/* First Argument: Next */
(value) => {
	console.log(
		'The first function is called whenever a value is emitted.', value
	)
},
/* Second Argument: Error */*
(error) => {
	console.error(
		'The second function is called if an error shows up in the observable.', error
	)
},
/* Third Argument: Complete */*
() => {
	console.log(
		'The third function is called whenever the observable completes.'
	)
}
)

// New Syntax

// Use this when you care only about the next values.
example$.subscribe((value) => console.log('Emitted',value))

// Use this when you explicitly care about either the error or when the observable completes.
example$.subscribe({
	next: (value) => console.log('Emitted', value),
	error: (error) => console.log('Error', error),
	complete: () => console.log('Completed')
})
```


`fromEvent` : Create observables based on event listeners.

```js
const button = document.querySelector('button')

button.addEventListener('click', (event) => {
	console.log(event)
})

const buttonClicks$ = fromEvent(button, 'click')

buttonClicks$.subscribe(console.log)

// Optionally we can pass a function to fromat the event

fromEvent(input, ,'input', (event) => {
event.target.value
})
```


`bindCallback` : Turn anything that takes a callback into an observable

```js
const get = bindCallback(jQuery.get);
const data$ = get('/api/endpoint')

const readFile = bindNodeCallback(fs.readFile)
const content$ = readFile('./groceries.md','utf-8')
```


`fromFetch` : Wrap the Fetch API in an observable.

```js
const data$ = fromFetch('/api/endpoint')
```

---
## Intervals and Timers

`interval` : Creates an observable that emits an event every n milliseconds.

```js
const {interval} = require('rxjs')
const startingTime = Date.now()
const tick$ = interval(1000)

tick$.subscribe(() => console.log(Date.now() - startingTime))
```


`timer` : Create an observable that emits after a certain amount of time.

```js
const {timer} = require("rxjs")

const startingTime = Date.now()
const tick$ = timer(5000)

tick$.subscribe(() => console.log(Date.now() - startingTime))

// Timers can also continue to emit at regular intervals

const startingTime = Date.now()
const tick$ = timer(2000, 5000)

tick$.subscribe(() => console.log(Date.now() - startingTime))
```


`unsubscribe` : You should be able to clean up after yourself. 

```js
const interval$ = interval(1000)
const subscription = interval$.subscribe(console.log)

setTimeout(() => subscription.unsubscribe(), 5000)
```

---

## Operators

### Manipulating the Stream
Each observable has a `.pipe` method.

- This method takes one or more functions called operators.
- Each operator takes the observable, does something to it, and returns a new observable.
- This is similar to method chaining.

`take` : Take a certain number of values from an observable and then stop.
- We can choose how many values we want from an event

```js
const example$ = from(fibonacci()).pipe(take(10))
example.subscribe((val) => console.log(val))
```


`skip` : Ignore the first however many values.

```js
const example$ = from(fibonacci()).pipe(skip(2))
example.subscribe((val) => console.log(val))
```


`takeWhile` & `skipWhile` : Take or skip values as long a certain condition is met. Complete the observable when the condition returns false.

```js
const under200$ = from(fibonacci()).pipe(
	takeWhile(value => value < 200)
)
under200$.subscribe(console.log)

const over200$ = from(fibonacci()).pipe(
	skipWhile(value => value < 100)
)
under100$.subscribe(console.log)
```


`filter` : This works just like it does on arrays

```js
const evenNumbers$ = of(1,2,3,4,,5,6,7,8,9).pipe(
	filter((n) => n % 2 === 0)
)

evenNumbers$.subscribe((val) => console.log(val))
```


`map` : Applies a given `project` function to each value emitted by the source

```js
const doubledNumbers$ = of(1, 2, 3).pipe(map((n) => n*2))

doubledNumbers$.subscribe(console.log)
```


`mapTo` : Simplified version of map

```js
const over100$ = from(fibonacci()).pipe(
	skipWhile((value) => value < 100),
	take(4),
	mapTo('HELLO!')
)
over100$.subscribe(console.log)
```


`reduce` : 

`scan` :

`tap` : Incredibly useful for side-effects like DOM manipulation and debugging.

`takeUntil` & `skipUntil` : These operators rely on other observables. When the observable that they're subscribing to triggers, they will activate.

---

## Manipulating Time

`delay` : 

`throttleTime` :

`debounceTime` : 

`throttle` : 

`debounce` :

`merge` :

`combined` :

`concat` :

`race` :

---

## Higher Order Observables

### Returning Observables


`mergeAll` : Takes a stream of branch observables and merges them into the main timeline.

`concatAll` : Similar to `mergeAll` , but it plays through the observables in order

### Mapping Operators

We have four major kinds of mapping operators.

- `mergeMap` : 
- `concatMap` :
- `switchMap` : 
- `exhaustMap` :

`combineLatestAll` : 

`combineLatestWith` :

---

## Fetching from an API

`catchError` :

