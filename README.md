## Requirements
- Node v20. If you use `nvm`, you should be able to run `nvm use` from the root to set it up easily.
- Yarn. Run `yarn install` to get all the packages needed.


## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Type Support For `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin) to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) that is more performant. You can enable it by the following steps:

1. Disable the built-in TypeScript Extension
   1. Run `Extensions: Show Built-in Extensions` from VSCode's command palette
   2. Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2. Reload the VSCode window by running `Developer: Reload Window` from the command palette.

---

## Solution – Tree Structure Implementation

This solution implements a recursive `TreeItem` Vue component to render the hierarchical structure from the `fetchData.ts` data.

### Time spent
Approximately 45 minutes, including setup, implementation, and minor adjustments.

### Technical choices and reasoning
- I used a **recursive Vue component** (`TreeItem.vue`) to display items with nested children (more elegant and scalable way to handle unknown levels of nesting in a tree structure).
- The data is fetched asynchronously in the `created()` hook using the `fetchData()` function. Once resolved, the component state is updated with the result.
- Toggle logic is handled simply using Unicode characters (`▶` / `▼`).
- Since I previously implemented a **page builder in Vue** that heavily relied on recursive structures, the logic here felt natural and straightforward.
