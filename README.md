# recruitment-task-button

## This is simple program created for recruitment purposes that solves the following task:

There is a simple button component to prepare based on the
design (https://www.figma.com/file/uhXRwrgKMeIwhO8fjTDyYs/Untitled?type=design&node-id=0%3A1&mode=design&t=0FIlkceKOMQi4oBz-1)
The component should be written in Vue3 with using TypeScript and Composition API. The button should:

* be able to be displayed as button, a or router-link
* if displayed as a, you can pass the href attribute to it
* if it is displayed as router-link, you can pass the to attribute to it
* comes in 3 sizes (each button style regardless of variant
  stylistic has the same dimensions): small, regular(default), large
* comes in 2 stylistic variants: filled (default), outlined
* has the option of displaying in block mode (100% width + centered
  horizontal content)
* has a disabling option (disabled attribute), which: makes the button not clickable, makes the button visually gray and
  less visible (opacity .4) and no hover or focus effects work (not only visually)
* the button should give the user visual feedback at the moment of :hover and :focus
* button content should be limited to one line height + w
  if you insert elements other than text (e.g. image/icon)
  should be centered vertically to each other
* buttons of the same size next to each other should always have the same size
  dimension (height) regardless of the stylistic variant
* buttons of different sizes should always be next to each other
  centered on the current line:
* report the following events: click - when clicking on a button that is not disabled,
  the event argument should be a native event from the browser

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and
disable
Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for
type checking. In editors, we
need [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin)
to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented
a [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) that is more
performant. You can enable it by the following steps:

1. Disable the built-in TypeScript Extension
    1) Run `Extensions: Show Built-in Extensions` from VSCode's command palette
    2) Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2. Reload the VSCode window by running `Developer: Reload Window` from the command palette.

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
