---
Order: 8
Area: nodejs
TOCTitle: Vue Tutorial
ContentId: 85ce0bcc-d2b8-4b7c-b744-5eddce9a8d00
PageTitle: Vue JavaScript Tutorial in Visual Studio Code
DateApproved: 3/30/2022
MetaDescription: Vue JavaScript tutorial showing IntelliSense, debugging, and code navigation support in the Visual Studio Code editor.
---

---

![welcome to Vue](images/vuejs/welcome-to-vue.png)

---

# Using Vue in Visual Studio Code

[Vue.js](https://vuejs.org/) is a JavaScript framework for building user interfaces. It builds on top of standard [HTML](/docs/languages/html.md), [CSS](/docs/languages/css.md), and [JavaScript](/docs/languages/javascript.md), and provides a declarative and component-based programming model that helps you efficiently develop user interfaces, be it simple or complex.

The recommended IDE setup is Visual Studio Code + [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar) extension. Volar provides syntax highlighting, Typescript support, and intellisense for template expressions and component props. There is also devtools extension for the web browser but a stand-alone electron app is also available.

## Recommended IDE setup

<table>
  <tr>
    <th>
      <a href="https://vuejs.org/guide/scaling-up/tooling.html#project-scaffolding">Project Scaffolding/CLI</a>
    </th>
    <th>
      <a href="https://vuejs.org/guide/scaling-up/tooling.html#project-scaffolding">VS Code Extension</a>
    </th>
    <th colspan="3">
      <a href="https://vuejs.org/guide/scaling-up/tooling.html#browser-devtools">Browser Devtools</a> <a href="https://devtools.vuejs.org/">[Documentation]<a>
    </th>
  </tr>
  <tr>
    <td>
      <a href="https://vitejs.dev/">Vite</a>
    </td>
    <td>
      <a href="https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar">Volar</a>
    <td>
      <a href="https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd">Chrome Browser extension</a>
    </td>
    <td>
      <a href="https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/">Firefox Browser Extension</a>
    </td>
    <td>
      <a href="https://devtools.vuejs.org/guide/installation.html#settings-1">Standalone Electron App</a>
    </td>
  </tr>
</table>

> **Tip** [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar) replaces [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur), the previous official VSCode extension for Vue 2. If you have Vetur currently installed, make sure to disable it in Vue 3 projects.

It is also recommmended to use the Vue browser devtools extension which allows you to explore a Vue app's component tree, inspect the state of individual components, track state management events, and profile performance.

<img src="https://raw.githubusercontent.com/vuejs/devtools/main/media/screenshot-shadow.png" alt="devtools screenshot"/>![image](https://user-images.githubusercontent.com/77064515/158494523-5e435f01-72b6-4136-95b2-615b52d01326.png)

## Other Tools

<table>
<tr>
  <th colspan="2">
    <a href="https://vuejs.org/guide/scaling-up/tooling.html#linting">Linting</a> <a href="https://eslint.vuejs.org/">[Documentation]</a>
  </th>
  <th>
    <a href="https://vuejs.org/guide/scaling-up/tooling.html#formatting">Formatting</a>
  </th>
  <th colspan="3">
    <a href="https://vuejs.org/guide/scaling-up/tooling.html#testing">Testing</a> <a href="https://vuejs.org/guide/scaling-up/testing.html">[Guide]</a>
  </th>
  </tr>
  <tr>
    <td><a href="https://eslint.vuejs.org">eslint-plugin-vue</a></td>
    <td><a href="https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint">VS Code Extension</a></td>
    <td>
    <i>The <a href=https://vuejs.org/guide/scaling-up/tooling>Volar</a> VS Code extension provides formatting for Vue SFCs out of the box. Alternatively, <a href="https://vuejs.org/guide/scaling-up/tooling">Prettier</a> provides built-in SFC formatting support.</i>
    </td>
    <td><a href="https://www.cypress.io/">Cypress</a></td>
    <td><a href="https://vitest.dev/">Vitest</a></td>
    <td><a href="https://jestjs.io/">Jest</a></td>
  </tr>
</table>

---

## Welcome to Vue

We'll be using Vite for this tutorial. Vite is a lightweight and fast build tool with first-class Vue SFC support and recommended to scaffold a Vue project unless you rely specifically on webpack-only features. Vite will provide superior developer experience in most cases in comparison to [Vue CLI](https://cli.vuejs.org/) primarily used with Vue v2 (Please see Vue Version section for more information). [Vue CLI](https://cli.vuejs.org/) is available as the official webpack-based toolchain for Vue in maintenance mode. For more information on migrating from Vue CLI to Vite:

> **Tip** Recently the default version of Vue changed to version 3 as of **Monday, February 7, 2022**. While [Vue CLI](https://cli.vuejs.org/) is still available in maintenance mode, Vite is recommended as the preferred tool to scaffold new Vue projets. For more details concerning the Vue 2 to Vue 3 migration please refer to the [Vue Version](vuejs-tutorial.md#Vue-Version) section.

To create a build-tool enabled Vue project on your machine, run the following command in your command line (without the > sign):

```bash
npm init vue@latest
```

---

---

## Vue Version

Vue 3 has been distinguished as the new default version as of **Monday, February 7, 2022**. As a result certain changes have been implemented concerning recommended practices as well as updated references for documentation. For more details please review the following [article](https://blog.vuejs.org/posts/vue-3-as-the-new-default.html) and in summary the following changes have occurred which could invoke breakages concerning Vue 2 deployment and development.

### npm dist tags

`npm install vue` now installs Vue 3 by default.
The `latest` dist tag of all other official npm packages now point to Vue 3 compatible versions, including `vue-router`, `vuex`, `vue-loader`, and `@vue/test-utils`.

### Official docs and sites

All documentation and official sites now default to Vue 3 versions. The Vue 2 versions of these sites have ben moved to new addresses (the version prefixes indicate the libraries' respective versions, not Vue core's):

| Vue 3                                                               | Vue 2                                                                   |
| ------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| [vuejs.org](https://vuejs.org/)                                     | [v2.vuejs.org](https://v2.vuejs.org)                                    |
| [router.vuejs.org](https://router.vuejs.org/)                       | [v3.vuerouter.vuejs.org](https://v3.vuerouter.vuejs.org)                |
| [vuex.vuejs.org](https://vuex.vuejs.org/)                           | [v3.vuex.vuejs.org](https://v3.vuex.vuejs.org)                          |
| [test-utils.vuejs.org](https://test-utils.vuejs.org)                | [v1.test-utils.vuejs.org](https://v1.test-utils.vuejs.org)              |
| [template-explorer.vuejs.org](https://template-explorer.vuejs.org/) | [v2.template-explorer.vuejs.org](https://v2.template-eplorer.vuejs.org) |

### GitHub repos

All Github repos under the `vuejs` organization have switched to Vue 3 versions in the default branch. In additon the following repos have had `next` removed in their names:

| Previous Branch Name                                                        | Default Branch Name                                                    |
| --------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| [`vuejs/vue-next`](https://github.com/vuejs/vue-next)                       | [`vuejs/core`](https://github.com/vuejs/core)                          |
| [`vuejs/vue-router-next`](https://github.com/vuejs/vue-router-next)         | [`vuejs/router`](https://github.com/vuejs/router)                      |
| [`vuejs/docs-next`](https://github.com/vuejs/docs-next)                     | [`vuejs/docs`](https://github.com/vuejs/docs)                          |
| [`vuejs/vue-test-utils-next`](https://github.com/vuejs/vue-test-utils-next) | [`vuejs/test-utils`](https://github.com/vuejs/docs)                    |
| [`vuejs/jsx-next`](https://github.com/vuejs/jsx-next)                       | [`vuejs/babel-plugin-jsx`](https://github.com/vuejs/babel-plugin-jsx`) |

Translation repose for the main documentation are moved to the [`vuejs-translations` organization](https://github.com/vuejs-translations).

### Devtools Extension

Devtools v6, which was previously published under the [beta channel](https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg) on the Chrome Web Store, is now published under the [stable channel](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd). The previous version of the devtools extension is still available and has been moved to the [legacy channel](https://chrome.google.com/webstore/detail/vuejs-devtools/iaajmlceplecbljialhhkmedjlpdblhp).

### IDE Support

The recommended IDE setup is [VSCode](https://code.visualstudio.com/) + the [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar) extension. Volar provides syntax highlighting, Typescript support, and intellisense for template expressions an component props.

> **Tip**: [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar) replaces [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur), our previous official VSCode extension for Vue 2. If you have Vetur currently installed, make sure to disable it in Vue 3 projects.

### Project Scaffolding

[Vue CLI -> Vite Migration Guide from VueSchool.io](https://vueschool.io/articles/vuejs-tutorials/how-to-migrate-from-vue-cli-to-vite/)
[Tools / Plugins that help with auto migration](https://github.com/vitejs/awesome-vite#vue-cli)

---

## Volar extension

Now expand the `src` folder and select the `App.vue` file. You'll notice that VS Code doesn't show any syntax highlighting and it treats the file as **Plain Text** as you can see in the lower right Status Bar. You'll also see a notification recommending the [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur) extension for the `.vue` file type.

![vetur extension recommendation](images/vuejs/vetur-extension-recommendation.png)

The Vetur extension supplies Vue.js language features (syntax highlighting, IntelliSense, snippets, formatting) to VS Code.

![vetur extension](images/vuejs/vetur-extension.png)

From the notification, press **Install** to download and install the Vetur extension. You should see the Vetur extension **Installing** in the Extensions view. Once the installation is complete (may take several minutes), the **Install** button will change to the **Manage** gear button.

Now you should see that `.vue` is a recognized file type for the Vue language and you have language features such as syntax highlighting, bracket matching, and hover descriptions.

![vue language features](images/vuejs/vue-language-features.png)

## IntelliSense

As you start typing in `App.vue`, you'll see smart suggestions or completions both for HTML and CSS but also for Vue.js specific items like declarations (`v-bind`, `v-for`) in the Vue `template` section:

![Vue.js suggestions](images/vuejs/suggestions.png)

and Vue properties (`methods`, `computed`) in the `scripts` section:

![Vue.js JavaScript suggestions](images/vuejs/javascript-suggestions.png)

### Go to Definition, Peek definition

VS Code through the Vue extension language service can also provide type definition information in the editor through **Go to Definition** (`kb(editor.action.revealDefinition)`) or **Peek Definition** (`kb(editor.action.peekDefinition)`). Put the cursor over the `App`, right click and select **Peek Definition**. A [Peek window](/docs/editor/editingevolved.md#peek) will open showing the `App` definition from `App.js`.

![Vue.js peek definition](images/vuejs/peek-definition.png)

Press `kbstyle(Escape)` to close the Peek window.

## Hello World!

Let's update the sample application to "Hello World!". In `App.vue` replace the HelloWorld component `msg` custom attribute text with "Hello World!".

```html
<template>
  <div id="app">
    <img src="./assets/logo.png" />
    <HelloWorld msg="Hello World!" />
  </div>
</template>
```

Once you save the `App.vue` file (`kb(workbench.action.files.save)`), restart the server with `npm run serve` and you'll see "Hello World!". Leave the server running while we go on to learn about Vue.js client side debugging.

> **Tip**: VS Code supports Auto Save, which by default saves your files after a delay. Check the **Auto Save** option in the **File** menu to turn on Auto Save or directly configure the `files.autoSave` user [setting](/docs/getstarted/settings.md).

---

![hello world](images/vuejs/hello-world.png)

---

## Linting

Linters analyze your source code and can warn you about potential problems before you run your application. The Vue ESLint plugin ([eslint-plugin-vue](https://www.npmjs.com/package/eslint-plugin-vue)) checks for Vue.js specific syntax errors which are shown in the editor as red squigglies and are also displayed in the **Problems** panel (**View** > **Problems** `kb(workbench.actions.view.problems)`).

Below you can see an error when the Vue linter detects more than one root element in a template:

![Vue linting](images/vuejs/vue-linting.png)

## Debugging

You can debug client side Vue.js code with the built-in JavaScript debugger. You can learn more from the [Vue.js debugging in VS Code](https://github.com/microsoft/vscode-recipes/tree/main/vuejs-cli) recipe on the VS Code debugging [recipes](https://github.com/microsoft/vscode-recipes) site.

> Note: There are currently issues with the sourcemaps generated by vue-cli, which cause issues with the debugging experience in VS Code. See [https://github.com/vuejs/vue-loader/issues/1163](https://github.com/vuejs/vue-loader/issues/1163).
> Another popular tool for debugging Vue.js is the [vue-devtools](https://github.com/vuejs/vue-devtools) plug-in.

## Other extensions

Vetur is only one of many Vue.js extensions available for VS Code. You can search in the Extensions view (`kb(workbench.view.extensions)`) by typing 'vue'.

![Vue.js extensions](images/vuejs/vue-extensions.png)

There are also Extension Packs which bundle extensions that other people have found useful for Vue.js development.

![Vue.js extension pack](images/vuejs/vue-extension-pack.png)
