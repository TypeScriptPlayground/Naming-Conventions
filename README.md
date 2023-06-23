[L001]: https://en.wikipedia.org/wiki/Camel_case
[L002]: https://en.wikipedia.org/wiki/Snake_case
[L003]: https://en.wikipedia.org/wiki/All_caps

# Naming-Conventions
These are some rules for my TypeScript projects.

## Basics
### Filename
All filenames are written in [snakecase][L002] style. In the file name, letters from lower case `a-z` and `_` are allowed. Use numbers `0-9` only if it is necessary. For example, if the function is called `encodeBase64`.
> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```
> encode_base64.ts
> ```


### Foldername
In the folder name, letters from lower case `a-z` and `_` are allowed. **Never** use numbers to sort folders. For example, `01_help`, `02_error`, `03_components`, ...

### Filecontent
A file should have only one main `function`/`class`/`object`/`type` which is exported. The `function`/`class`/`object`/`type` should then be named exactly like the file name, in [camelcase][L001]. 

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> For example, if we want to write a function that reads a text file, we would name the file `read_text_file.ts`. In the file we would then export a function which looks like this.
> ```ts
> export default function readTextFile() : string {
>   //...
> }
> ```
> Function name `readTextFile()` becomes Filename `read_text_file.ts`.

Helper `functions`/`objects` for the main function that gets exportet are allowed. It is also allowed to export an object and a type as long as the type is created from the object. You can look up the reason for this under [enum](#enum).

A file may contain a maximum of 100 lines of code and a maximum of 3-4 indentations. If the number of lines or the number of indentations is exceeded, then the code must be outsourced to individual functions in separate files. This keeps the code within a file more readable. This rule does not apply to data structures as for example `json` files.


<br>

## Variables
All variables are written in [camelcase][L001].

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const fooBar = 'Hello World';
> let barFoo : number;
> ```

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

<br>

### object
Object names are written in [camelcase][L001]. The same is applied to object members. 

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const obj = {text: 'Hello World!'}
> ```

If there is more than one member in the object, each member must be wrapped to a new line. It is also allowed to wrap the member of an object to a new line if the object has only one member.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const obj = {
>   text: 'Hello World!',
>   value: 42
> }
> ```

<br>

### interface
Interface names are started with a capital letter. The rest of the name is written in [camelcase][L001]. Variable definitions are separated by a comma.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> interface FooBar {
>   text : string,
>   value : number
> }
> ```

<br>

### enum
Enum names are written in [camelcase][L001]. Enum variables are written in [all caps][L003].

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> enum textTypes {
>   TEXT_A,
>   TEXT_B
> }
> ```

Avoid using enums as presets for default values. Use objects instead. Always export these objects `as const`.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> export const textTypes = {
>   TEXT_A: 0,
>   TEXT_B: 1
> } as const
> 
> export typeof TextType[keyof typeof textTypes]
> ```

<br>

### function
Function names are written in [camelcase][L001].

#### Normal function: `function func(param : string) {}`

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> function func(param : string) {
>   //...
> }
> ```

#### Anonymous function: `function() {}`
#### Arrow function: `() => {}`



