# Typescript Cheatsheet

## Table of contents

<!-- vim-markdown-toc GFM -->

- [tsc commands](#tsc-commands)
- [tsconfig file](#tsconfig-file)
- [Debugging ts](#debugging-ts)
- [Functions](#functions)
- [Type alias](#type-alias)
  - [Optional chaining](#optional-chaining)
  - [Optional property access operator](#optional-property-access-operator)
  - [Optional element access operator](#optional-element-access-operator)
  - [Optional call](#optional-call)
- [Nullish coalescing operator](#nullish-coalescing-operator)
- [Destructuring](#destructuring)

<!-- vim-markdown-toc -->

## tsc commands

- Compile a ts file into a js file.

```
tsc <program_name>
```

**Note**: with a `tsconfig.json` file specifying the `<program_name>` becomes unnecessary, since the _root directory_ of the ts project is specified in the config file.

- Create a `tsconfig.json` file.

```
tsc --init
```

## tsconfig file

- Important parameters
  - `rootDir` : root directory with ts files, usually at `./src`
  - `outDir` : directory for output files, usuallt at `./dist`
  - `noEmitOnError` : set to `true` so that the compiler does not output any js code when errors are detected.
  - `sourceMap`: set to `true` to enable debugging.
  - `noUnusedParameters`
  - `noUnusedLocals`
  - `noImplicitAny`
  - `noImplicitReturns`: Compiler forces you to annotate return type(s) of functions.
  - `allowUnreachableCode`: `false`

## Debugging ts

1. Set the `sourceMap` option to `true` in the tsconfig file.
2. A `.js.map` will be created after compilation in the `outDir`.
3. Create a `launch.json` file in VSC.
   - Add the parameter `"preLaunchTask": "tsc: build - tsconfig.json",` above `outputFiles` in the `launch.json` file. This will make the debugger use the appropriate config file.

## Functions

```ts
function render(num: number, str: string): number {
  console.log(str);
  return num;
}
```

- Make a parameter optional. `str` will be optional.

```ts
function render(num: number, str?: string): number {
  if (str) console.log(str);
  return num;
}
```

- Give a parameter a default value (in case the parameter is not initialized, then it will have the default value). `str` will have the default value of `"hola"`.

```ts
function render(num = 7, str = "hola"): number {
  if (str) console.log(str);
  return num;
}
```

## Type alias

Define a certain type alias with given restrictions and re-use the definition through the codebase when initializing variables.

The `readonly` keyword allows a field to only be modified once.

```ts
type Employee = {
    readonly name: string,
    id: number,
    RetireAge: (age: number) => void,
}

let Ron: Employee = {
    name: "Ron",
    id: 1,
    RetireAge: (age: number) => {
        console.log(age);
    }
}
}
```

## Optional chaining

### Optional property access operator

Only if the expression before the `?` operator is **NOT** _null_ or _undefined_, the expression afterwards gets executed.

```ts
type Person = {
  id: number | undefined;
};

let Ron: Person = {
  id: 8,
};

console.log(Ron?.id);
```

### Optional element access operator

Only if the expression before the `?` operator is a **NOT** _null_ or _undefined_ **ARRAY**, the expression afterwards gets executed.

```ts
customer?.[0];
```

### Optional call

Only if the function before the `?` operator is **NOT** _null_ or _undefined_, the function afterwards gets executed.

```ts
let f: () => number = () => {
  console.log(4);
};

f?.();
```

## Nullish coalescing operator

If the previous value of the `??` operator is **NOT** `null` or `undefined`, we use the previous value, otherwise the value to the right of `??` is used.
In other words, it is very useful to set a default value (value on the right) in case no valid value is found.

```ts
let a: number | null = null;

let b: number = a ?? 40;
```

## Destructuring

### Arrays

```ts
const [one, two] = [1, 2, 3];
```

This is used frequently in React for the `useState` hook:

```ts
const [text, setText] = useState<string>("text");
```

Skip indexes:

```ts
const [, , three] = [1, 2, 3];
```

Store the remaining elements into a new array:

```ts
const [one, remaining] = [1, 2, 3];
// remaining = [2, 3];
```

### Objects

```ts
const person = {
  name: "Joan",
  lastName: "Miró",
  age: 79,
};

const { name, lastName, age } = person;
```

The variables `name`, `lastName` and `age` will contain the values in the properties of `person`.

If the value of a property is not provide it can be set to a default value:

```ts
const woman = {
  name: "Lisa",
  age: 94,
};

const { name, lastName = "Gutierrez", age } = woman;
```

One can also rename the name of a property by writing a new name for the variable after a colon `:`

```ts
const cat = {
  name: "Gaspar",
  age: 20,
  personality: "funny",
};

const { personality: character } = cat;
```

It is also possible to destructure nested object:

```ts
const nested = {
  parent: {
    child: "name of child",
  },
};

const {
  parent: { child },
} = nested;
```

The variable `child` corresponds to the value stored in the nested structure of the `nested` object.
