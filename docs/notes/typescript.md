# TypeScript Notes

## Basic Types

### Primitives

```ts linenums="1"
let userName: string = "Jack";
let hasLoggedIn: boolean = true;
let myNumber: number = 10;
```

### Arrays

```ts linenums="1"
const names: string[] = userName.split(" ");
const myValues: Array<number> = [1, 2, 3];
```

### Regex

```ts linenums="1"
let myRegex: RegExp = /foo/;
```

### Interfaces

```ts linenums="1"
interface Person {
    first: string;
    last: string;
}

const myPerson: Person = {
    first: "Jack",
    last: "Herring",
}
```

### Utilities

```ts linenums="1"
cons ids: Record<number, string> = {
    10: "a",
    20: "b",
}

ids[30] = "c";
```
