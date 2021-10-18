# console.log() in Javascript

## log level

- `console.log();` - use on development, delete before publishing
- `console.info();` - use for info, delete before publishing
- `console.warn();`
- `console.error();`

## assert with condition

- `console.assert(2 === 3, 'not same!');` - output: `Assertion failed: not same!`
- `console.assert(2 === 2, 'same!');` - no output

## print object

`const dog = { type: 'dog', name: 'chuchu', owner: { name: 'John'} };`

- `console.log(dog);`
- `console.table(dog)` - table output
- `console.dir(dog, {colors: false, depth: 0});` - output: `{ type: 'dog', name: 'chuchu', owner: [Object] }`

## measuring time

- ```js
  console.time('for loop');
  for (let i = 0; i < 10; i++) {
    i++;
  }
  console.timeEnd('for loop');
  ```
  - output: `for loop: 0.063ms`

## counting

- ```js
  function a() {
    console.count('a function');
  }
  a();
  a();
  console.countReset('a function');
  a();
  ```
  - output
  ```
  a function: 1
  a function: 2
  a function: 1
  ```

## trace

- Checking where it's called and when
- ```js
  function f1() {
    f2();
  }
  function f2() {
    f3();
  }
  function f3() {
    console.trace();
    console.log('hi!');
  }
  f1();
  ```
