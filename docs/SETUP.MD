# Project setup

This documents the basic setup of this project, which can be helpful when setting up something similar from scratch, and explain some inconsistencies with expectations.

## Step-by-step

- In a blank directory initialize a new project to create the `package.json`
  - `npm --init`
- Install Typescript dependencies and generate the `tsconfig.json`
  - `yarn add typescript`
  - `./node_modules/.bin/tsc --init`
  - `yarn add -D @types/node`
  - Edit the `tsconfig.json` to enable sourcemaps and set the `outDir` to something that makes sense (here, we're following the CRA convention and calling it `./build`)

- Install nodemon, wire it up, and add a build task
  - `yarn add -D nodemon`
  - Add to the `script` section in package.json the lines

    ```json
    "watch": "tsc && nodemon ./build/index.js",
    "build": "tsc"
    ```

- Install eslint and related plugins
  - `yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin`
  - Create the `.eslintrc.js` file (copy the one from here and customize as you please)
- Add prettier and related plugins
  - `yarn add -D prettier eslint-config-prettier eslint-plugin-prettier`
  - Create the `.prettierrc.js` file (copy the one from here and customize as you please)
- If using VSCode, create the file `.vscode/setting.json` similar to the one in here
- Initialize a git repository
  - `git --init`
  - Create the `.gitignore` file (the one here is the one created by GitHub for Node projects)
- Restart VSCode and check that things are working
  - ESLint status can be checked from `OUTPUT > ESLint`
  - Run the `watch` and `build` tasks

## References

The following web resources served as guides:

- [Setting up a new Typescript project](https://alligator.io/typescript/new-project/)
- [Using ESLint and Prettier in a Typescript project](https://alligator.io/typescript/new-project/)
- [Adding nodemon and debug support](https://medium.com/aherforth/how-to-get-auto-restart-and-breakpoint-support-with-typescript-and-node-5af589dd8687)
