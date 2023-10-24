[L001]: https://en.wikipedia.org/wiki/Camel_case
[L002]: https://en.wikipedia.org/wiki/Snake_case
[L003]: https://en.wikipedia.org/wiki/All_caps
[L004]: https://en.wikipedia.org/wiki/Pascal_case

[L010]: https://www.typescriptlang.org/docs/handbook/declaration-files/templates/module-d-ts.html
[L011]: https://jsdoc.app/

# Naming-Conventions
These are some rules for my TypeScript projects.

## Directory

### Filename
All filenames are written in [snakecase][L002] style. In the file name, letters from lower case `a-z` and `_` are allowed. Use numbers `0-9` only if it is necessary. For example, if the function is called `encodeBase64`.
> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> The filename would look like this:
> ```
> encode_base64.ts
> ```

### Foldername
In the folder name, letters from lower case `a-z` and `_` are allowed. **Never** use numbers to sort folders. For example, `01_help`, `02_error`, `03_components`, ...

### Filecontent
A file should have only one main `function`/`class` which is exported. The `function`/`class` should then be named exactly like the file name, in [camelcase][L001]. If you have an object that mimics an `enum` then the associated type of this object will be exported as well. You can read more about this in the [enum](#enum) section.

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

#### Helpers/Untilities
Helper `functions`/`objects` for the main function that gets exportet are allowed. It is also allowed to export an object and a type as long as the type is created from the object. You can look up the reason for this under [enum](#enum).

#### Vertical character limit
A file may contain a maximum of **<ins>30</ins>** lines of code (excluding comments and whitespace between lines). This is for increasing readability. If the number of lines or the number of indentations is exceeded, then the code must be refactored to separate files. This rule does not apply to data structures as for example `json` files.

#### Horizontal character limit
The maximum character limit for a line is **<ins>120</ins>** characters and a maximum of **<ins>4</ins>** indentations.

<br>

## Documentation/Comments
All TypeScript files are documented in the [JSDoc][L011] format.

<br>

## Variables/Types
All variables are written in [camelcase][L001]. You can read more about that in the [`let`/`const`/`var`](#letconstvar) section.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const greeting = 'Hello World';
> let age : number;
> ```

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
> const object = {key: 'Text'};
> ```

<br>

## Declaration-Statements

### `let`/`const`/`var`
`let`/`const` names are written in [camelcase][L001]. The same is applied to members of objects. Avoid the use of `var`, use `let`/`const` instead.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const messageVariants = {greetingMessage: 'Hey, nice to see you.'}
> ```

If the object has more than one key or the key name exceeds the maximum [character limit](#character-limit) for a line then the line needs to be wrapped.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const messageVariants = {
>   greetingMessage: 'Hey, nice to see you.',
>   goodbyeMessage: 'Bye!'
> }
> ```

If you declare a variable whose content does not change, then this variable is written in [ALL_CAPS][L003]. This rule does not apply to objects described in other structures, like "enum like objects" in the [enum](#enum) section.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const API_ENDPOINT = 'https://api.example.com';
> ```

### `interface`
Interface names are started with a capital letter. The rest of the name is written in [camelcase][L001]. Also known as [PascalCase][L004]. Variable definitions are separated by a comma. Interfaces are always exported in a [`.d.ts`][L010] file. Each key in an interface needs to be on a separate line.

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

### `type`
...

### `enum`
Enum names are written in [camelcase][L001]. Enum variables are written in [all caps][L003]. Each key in an enum needs to be on a separate line.

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

Avoid using enums as presets for default values. Use enum like objects instead. Always export these objects `as const`.

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

### `function`
Function names are written in [camelcase][L001]. If the function has more than one parameter or the parameter name exceeds the maximum [character limit](#character-limit) for a line then the line needs to be wrapped. The same rule also applies to the content of the function. Always specify a return value for the function. The return value is specified in the same form as for a [type](#types).

#### Named functions
No space is inserted between the function name and the parentheses. A space is inserted between the return type and the curly brackets.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> function functionName(param : string) : void {
>   //...
> }
> ```

#### Anonymous functions
No space is inserted between the `function` keyword and the parentheses. A space is inserted between the return type and the curly brackets.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const fooBar = function(param : string) : void {
>   //...
> }
> ```

#### Arrow functions
A space is inserted between the parentheses and the arrow. A space is also inserted between the arrow and the curly brackets.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/example.svg">
>   <img alt="Example" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/example.svg">
> </picture><br>
>
> ```ts
> const fooBar = (param : string) : void => {
>   //...
> }
> ```

### `class`
...

### `namespace`
...

<br>

<br>

[↑ Back to top](README.md##)
