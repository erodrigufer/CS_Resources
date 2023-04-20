# Typescript Cheatsheet

## Table of contents
<!-- vim-markdown-toc GFM -->

* [tsc commands](#tsc-commands)
* [tsconfig file](#tsconfig-file)
* [Debugging ts](#debugging-ts)
* [Functions](#functions)
* [Type alias](#type-alias)
    - [Optional chaining](#optional-chaining)
    - [Optional property access operator](#optional-property-access-operator)
    - [Optional element access operator](#optional-element-access-operator)
    - [Optional call](#optional-call)
* [Nullish coaelscing operator](#nullish-coaelscing-operator)

<!-- vim-markdown-toc -->

## tsc commands

* Compile a ts file into a js file.

```
tsc <program_name>
```

**Note**: with a `tsconfig.json` file specifying the `<program_name>` becomes unnecessary, since the _root directory_ of the ts project is specified in the config file.

* Create a `tsconfig.json` file.

```
tsc --init
```

## tsconfig file

* Important parameters
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
function render(num : number, str : string) : number {
    console.log(str)
    return num
}
```

* Make a parameter optional. `str` will be optional.

```ts
function render(num : number, str?: string) : number {
    if (str)
        console.log(str)
    return num
}
```

* Give a parameter a default value (in case the parameter is not initialized, then it will have the default value). `str` will have the default value of `"hola"`.

```ts
function render(num=7 , str="hola") : number {
    if (str)
        console.log(str)
    return num
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
### Optional chaining

### Optional property access operator

Only if the expression before the `?` operator is **NOT** _null_ or _undefined_, the expression afterwards gets executed.

```ts
type Person = {
    id: number | undefined,
}

let Ron: Person = {
    id: 8,
}

console.log(Ron?.id)
```

### Optional element access operator

Only if the expression before the `?` operator is a **NOT** _null_ or _undefined_ **ARRAY**, the expression afterwards gets executed.

```ts
customer?.[0]
```

### Optional call

Only if the function before the `?` operator is **NOT** _null_ or _undefined_, the function afterwards gets executed.

```ts

let f: () => number = () => {
    console.log(4)
}

f?.()
```

## Nullish coaelscing operator


th `??` if the previous value is **NOT** _null_ or _undefined_, we use the previous value, otherwise the value to the right of `??` is used.

```ts
let a: number | null = null;

let b: number = a ?? 40
```
customer?.[0]
```
