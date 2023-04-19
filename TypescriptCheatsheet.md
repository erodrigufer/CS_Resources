# Typescript Cheatsheet

## Table of contents
<!-- vim-markdown-toc GFM -->

* [tsc commands](#tsc-commands)
* [tsconfig file](#tsconfig-file)

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

