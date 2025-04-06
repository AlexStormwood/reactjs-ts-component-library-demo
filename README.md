# ReactJS TypeScript Component Library Demo

Example repo to demonstrate how a ReactJS project built with Vite and TypeScript can be used to create and share components as a library - specifically, as an NPM package.

## Package Usage

Install this package with: 

`npm install @alexstormwood/reactjs-ts-component-library-demo`

Import the component with:

```js
import { ExampleComponent } from '@alexstormwood/reactjs-ts-component-library-demo';
```

Use the component with:

```jsx
<ExampleComponent />
```

## Package Build and Publish

To build this project's package, you must run: 

`npm run build:lib`

The package output is available in the `dist/` folder of the repository, and publishing to a registry such as NPM will publish a package with contents like:

- README.md
- LICENSE
- package.json
- dist/
	- index.js
	- index.d.ts
	- ...the rest of files and folders contained within the `dist/` folder

The package's `package.json` is configured to export the `dist/index.js` file already, so usage is handled as per above. 
Your `lib/index.ts` should provide the expected exports of the package to make that work though!

## Package Demo

A package made with this style of project structure will also be able to deploy as a demo website, from a website with source code in the `src` directory.

To build the demo website, you should run: 

`npm run build:demo`

To publish the website, you want to publish the contents of the `demo/` directory.

In Netlify, for example, your Build Settings configuration would look like:

- Branch: `main`
- Build command: `npm run build:demo`
- Publish directory: `demo`

And then your `src/` ReactJS app that demonstrates the usage of the package made in `lib/` would be available for all to see!