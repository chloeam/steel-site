# Steel Framework

Currently in progress.

Once this project is completed, it will be a UI pattern library featuring clean, minimal components and vertical rhythm, modular scale, and baseline-aligned text. It will build off of [Bourbon](http://bourbon.io/) and [Neat](http://neat.bourbon.io/).

It was made by [Chloe Atchue-Mamlet](http://chloeam.com/) using [Jekyll](http://jekyllrb.com/).

# Roadmap

- Multiple button sizes
- Buttons for various screen sizes
- Testing on every element
- Make sure mixin use is as efficient as possible

# Docs (Under Construction)

## Getting started

1. **Choose your typefaces**. Select your typefaces (Steel supports and encourages separate typefaces for body text, headings, and code) and update the maps in the `_variables.scss` partial to reflect your choices. Don't worry about the `cap-height` variable for now.

2. **Set type to the baseline**. Steel uses a modified version of [Sassline](https://sassline.com/) in order to accomplish this. The `cap-height` variable in `_variables.scss` allows us to align text to the baseline instead of having it sit between two baselines. In order to measure cap height, turn on the baseline grid by uncommenting the annotated section in `_globals.scss`. Then, experiment with changing the `cap-height` variable in `_variables.scss` until the bottom of the text aligns to the baseline for all window sizes. The cap height will most likely be between 0.6 and 0.8.

## Customizing Steel

Steel is extremely easy to customize to fit your needs. Simply change the values of variables in `_variables.scss` to your liking. Unless you need really heavy customization, that is the only file you need to edit.

## Mixin library

Steel has a robust mixin library to make calculations easier and allow you to get the look you want.

### Media queries

The breakpoints are defined in `_variables.scss`, but feel free to customize them to your liking. Breakpoints should be definined in pixels but will be outputted in ems.

Call the breakpoint mixin with `@include breakpoint(break-1)` where `break-1` is the first breakpoint set in `_variables.scss`, `break-2` is the second, and so on.

### Grid system

Steel uses [Bourbon Neat](http://neat.bourbon.io/) for the grid system. They have much more comprehensive [documentation](http://thoughtbot.github.io/neat-docs/latest/), but here is a basic run-down.

Neat is a flexible, 12-column grid system that supports nesting and shifting.

1. Each set of columns must be wrapped in an outer-container, which is included like this: `@include outer-container;`.

2. You place your columns inside outer-container with the number of columns you'd like your element to take up. For example, `@include span-columns(6)` means the element will take up half of the available width.

3. Add `@include omega()` to the last element in your row to delete the right margin so all your elements fit on a single row. This mixin also supports a variable number of elements. For example, use `@include omega(4n)` to apply the omega mixin to every fourth element.
