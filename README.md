# OpenUI5 Data Binding Tutorial

This app represents my own implementation of the openUI5 Data Binding tutorial at

https://sdk.openui5.org/ --> Get Started: Setup, Tutorials and Demo Apps --> Data Binding (https://sdk.openui5.org/topic/e5310932a71f42daa41f3a6143efca9c)

-- The scaffolding was created with the Easy-ui5 Yeoman generator

-- https://github.com/SAP/generator-easy-ui5

## Requirements

Either [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/) for dependency management.

## Preparation

Use `npm` (or `yarn`) to install the dependencies:

```sh
npm i
```

## Run the App

Execute the following command to run the app locally for development in watch mode (the browser reloads the app automatically when there are changes in the source code):

```sh
ui5 serve -o index.html
```

or 
```sh
ui5.cmd serve -o index.html
```

As shown in the terminal after executing this command, the app is then running on http://localhost:8080/index.html. A browser window with this URL should automatically open.

(When using yarn, do `yarn start` instead.)


## License

This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSE) file.

## Implemented Parts of the Tutorial

* [Done] Step 1: No Data Binding
* [Done] Step 2: Creating a Model
* Step 3: Create Property Binding
* Step 4: Two-Way Data Binding
* Step 5: One-Way Data Binding
* Step 6: Resource Models
* Step 7: (Optional) Resource Bundles and Multiple Languages
* Step 8: Binding Paths: Accessing Properties in Hierarchically Structured Models
* Step 9: Formatting Values
* Step 10: Property Formatting Using Data Types
* Step 11: Validation Using the Message Manager
* Step 12: Aggregation Binding Using Templates
* Step 13: Element Binding
* Step 14: Expression Binding
* Step 15: Aggregation Binding Using a Factory Function













## Build the App

### Unoptimized (but quick)

Execute the following command to build the project and get an app that can be deployed:

```sh
npm run build
```

The result is placed into the `dist` folder. To start the generated package, just run

```sh
npm run start:dist
```

Note that `index.html` still loads the UI5 framework from the relative URL `resources/...`, which does not physically exist, but is only provided dynamically by the UI5 tooling. So for an actual deployment you should change this URL to either [the CDN](https://openui5.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae) or your local deployment of UI5.

(When using yarn, do `yarn build` and `yarn start:dist` instead.)

### Optimized

For an optimized self-contained build (takes longer because the UI5 resources are built, too), do:

```sh
npm run build:opt
```

To start the generated package, again just run:

```sh
npm run start:dist
```

In this case, all UI5 framework resources are also available within the `dist` folder, so the folder can be deployed as-is to any static web server, without changing the bootstrap URL.

With the self-contained build, the bootstrap URL in `index.html` has already been modified to load the newly created `sap-ui-custom.js` for bootstrapping, which contains all app resources as well as all needed UI5 JavaScript resources. Most UI5 resources inside the `dist` folder are for this reason actually **not** needed to run the app. Only the non-JS-files, like translation texts and CSS files, are used and must also be deployed. (Only when for some reason JS files are missing from the optimized self-contained bundle, they are also loaded separately.)

(When using yarn, do `yarn build:opt` and `yarn start:dist` instead.)

## Check the Code

To lint the code, do:

```sh
npm run lint
```

(Again, when using yarn, do `yarn lint` instead.)
