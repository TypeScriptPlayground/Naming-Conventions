[L001]: https://en.wikipedia.org/wiki/Camel_case

# Naming-Conventions
## Basics
### Filename

All filenames are written in snake case style
```
example_function.ts
```

### Content
A file should have only one main `function`/`class`/`object` which is exported. The `function`/`class`/`object` should then be named exactly like the file name, in [camelcase][L001]. Helper `functions`/`objects` are allowed.

In the file name, letters from lower case `a-z` and `_` are allowed.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> For example, if we want to write a function that reads a text file, we would name the file `read_text_file.ts`. In the file we would then export a function which looks like this.
> ```ts
> export default function readTextFile() {
>   //...
> }
> ```
> Filename `read_text_file.ts` becomes function name `readTextFile()`.

<br>

## Variables


<br>

## Types
Spaces are inserted between a variable and the colon and between the colon and a type. 

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> let word : string;
> ```

When a value is assigned to a variable in an object, **no** space is inserted between the variable and the colon. This is to distinguish a direct type assignment from a value assignment.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const object = {
>   key: 'Text'
> };
> ```

### `interface`
Interface names are started with a capital letter. The rest of the name is written in [camelcase][L001].

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> interface FooBar {
>   //...
> }
> ```

### `enum`


<br>

## Statement: `function`
Function names are written in [camelcase][L001].

### Normal function: `function foo(param : string) {}`

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> function foo(param : string) {
>   //...
> }
> ```

### Anonymous function: `function() {}`
### Arrow function: `() => {}`



