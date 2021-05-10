# FlowJS-Cheat-Sheet
Flow is a static type checker for your JavaScript code. It does a lot of work to make you more productive. Making you code faster, smarter, more confidently, and to a bigger scale.

https://cheatsheetmaker.com/flow

### References

- [Flow website](https://www.saltycrane.com/flow-type-cheat-sheet/latest/) _(flow.org)_
- [Getting started with Flow](https://flow.org/en/docs/getting-started/) _(flow.org)_
- [Flow type cheatsheet](https://www.saltycrane.com/flow-type-cheat-sheet/latest/) _(saltycrane.com)_### [Examples] Function signature

```js
type Callback = (?Error, string) => any

function fetch (callback: Callback) {
  ···
}
```

### [Examples] Examples

```js
var myNumbers: Array<number> = [42]
function foo(): any { return 42 }
var b: boolean = false
var b: ?boolean = false  /* maybe */
var b: string | boolean = false

var a: Class<MyClass> = MyClass
var b: MyClass = new a()
```

### [Advanced features] React

```js
type Props = {
  bar: number,
}

type State = {
  open: boolean,
}

class Foo extends React.Component<Props, State> {
  // Component code
}
```

### [Advanced features] Comment syntax

```js
/*::
  export type Foo = { ... }
*/

function add(n /*: number */) { ... }
```

### [Advanced features] Imports

```js
import type { Person } from '../person'
import typeof Config from '../config'
```

```js
export type Person = { id: string }
```

### [Advanced features] Functions

```js
const callback: () => void = function () {}
```

```js
function filter<T> (
  list: Array<T>,
  callback: (item: T) => boolean
): Array<T> {
  ···
}
```

See: [Functions](https://flow.org/en/docs/types/functions/)


### [Advanced features] Interfaces

```js
interface Jsonable {
  toJSON(): string
}

class Foo {
  toJSON() { return '{}' }
}

(new Foo: Jsonable)
```

See: [Interfaces](https://flow.org/en/docs/types/interfaces/)

### [Advanced features] Generic classes

```js
class GenericClass<T> {
  x: T
  constructor (x: T) { ... }
}

var n: GenericClass<number> = new GenericClass(0)
```

See: [Generic classes](https://flow.org/en/docs/types/generics/#toc-classes-with-generics)

### [Advanced features] Type aliases

```js
type Tree = {
  foo: string,
  bar: number,
  qux: (foo: string, bar: number) => boolean
}

type Generic<T> = {
  foo: T
}
```

See: [Type aliases](https://flow.org/en/docs/types/aliases/)
