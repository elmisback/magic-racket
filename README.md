# Magic Racket for VS Code

This extension adds support for [Racket](http://www.racket-lang.org) to VS Code. With the newly added support for language server protocol, we're proud to say that Magic Racket is **the best** Racket extension for VS Code.

## Setting up

1. Install Magic Racket. You can do that from the [VS Code extension marketplace](https://marketplace.visualstudio.com/items?itemName=evzen-wybitul.magic-racket).
2. Install the [racket-langserver](https://github.com/jeapostrophe/racket-langserver) by runnning the following command:

    ```bash
    raco pkg install racket-langserver
    ```

    Or update it using

    ```bash
    raco pkg update racket-langserver
    ```

## Features

Magic Racket **does**

- Support Racket LSP through [racket-langserver](https://github.com/jeapostrophe/racket-langserver), which brings jump to definition, hover information and more
- Have nearly complete support for every valid Racket syntax: byte strings, regexps, define clauses, vectors... You name it, we have it
- Support highlighting of all of the standart functions in `#lang racket`
- Turn many little VS Code knobs and switches to provide you the best possible Racket-writing experience

...but at the same time **doesn't**:

- Get in your way by providing useless snippets
- Throw around colorization just for the sake of it
- Try to do everything. What can be left up on the LSP, or some other package, will be. Focus is key

### LSP Support

Magic Racket now supports [racket-langserver](https://github.com/jeapostrophe/racket-langserver). The current features are:

- Underline errors
- Jump to definition
- Find references
- Hover information

We're working on providing more details in this section: stay tuned!

### Syntax highlighting

The image shows a comparison of a testing file highlighted using a popular Racket VS Code extension (on the left) and by Magic Racket (on the right).

![Highlighting comparison](images/magic-vs-other.png)

As you can see, Magic Racket strives to be _correct_ and _consistent_ — and it supports most of the language features as well. In many ways, this extension was inspired by the highlighting in DrRacket, however, in some aspects it aims to be less minimalistic.

### REPL support

You can load and execute files in Magic Racket by using the icons in the top right corner of your editor (see the image below), or from the commands console in VS Code. You can open the list of all commands by pressing <kbd>`Cmd+Shift+P`</kbd> (or <kbd>`Ctrl+Shift+P`</kbd> if you're on Linux or Windows) and then search through them by typing. All of Magic Racket's commands are prefixed by `Racket:` to make the searching easier.

In Magic Racket, each file will have its own REPL in which it'll load everytime you use the `Racket: Load file in REPL` command. You can choose to mimic this behavior also for `Racket: Run file in terminal`, or you can run all files in one output terminal.

![REPL showcase](images/repl.gif)

The list of commands added by Magic Racket:

- `Racket: Execute selection in REPL`
  - Executes the selection(s) in the REPL. Available also by right-clicking the selection or by using the shortcut <kbd>Alt+Enter</kbd>.
- `Racket: Load file in REPL`
  - Loads the current file into its REPL, creating a new REPL in the process if the file doesn't have one yet. Does have its icon in the top right corner.
- `Racket: Run file in terminal`
  - Runs the whole file in a terminal, outside of REPL environment. Depending on user settings, the terminal will be either shared among all files (default), or the one that belongs to the file.
- `Racket: Open the REPL for the current file`
  - Shows the REPL belonging to the current file, or opens a new one if the file doesn't have one yet.
- `Racket: Show the output terminal for the current file`
  - Similarly to the command above, this one shows the output terminal of the current file.

You can set the names of the REPLs and output terminals in the settings.

### Minor QoL features

These aren't game-changers, but they certainly help.

- You can write a λ (lambda) by using the included snippet `lmb` or the shortcut <kbd>Option+\\</kbd> (or <kbd>Alt+\\</kbd> on Windows and Linux)
- VS Code recognizes the "words" in Racket correctly, meaning that moving among words using <kbd>Ctrl+Left</kbd> and <kbd>Ctrl+Right</kbd> works as expected, and so does the double-click word selection

## Configuration

Magic Racket's options can be found in the `Magic Racket` section in VSCode preferences. 

However, if you would like to change some VSCode option _only_ for Racket (e.g. if you don't like the predefined editor rulers), you can do so by directly adding them into a `[racket]` section in `settings.json`:

```json
"[racket]": {
    "editor.rulers": [],
    // some further Racket-specifig configuration
}
```

## Release notes

Please see the [changelog](CHANGELOG.md) for the information about the latest updates.

## Want to help us?

Firstly — that's great, thanks!
Please see [contributing](CONTRIBUTING.md) for the information about what we need
