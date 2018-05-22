my-react-app-starter
====================

create-react-app is a great toolkit. It removes a lot of boilerplate to manage. Though, a few features are not shipped by default because each developer has different needs.

If you tend to use the same kind of configuration / devDependencies accross all of your create-react-app based projects, there isn't a perfect solution. This project is an attempt to fix this problem and share it with you.

## What's in it ?

I added the specific configuration / devDependencies I tend to use on my projects, such as:

* eslint with advanced rules such as config-airbnb + prettier with precommit hook
* local test server
* add metadatas in `index.html`
* `generate-changelog` npm run task
* deploy to github-pages npm run task

Each feature added can be identified by its commit, if you want to repeat only one of the steps on your own project.

This configuration has been inspired by [topheman/npm-registry-browser](https://github.com/topheman/npm-registry-browser), a project where I use all of the above (and more).

**This remains an un-ejected create-react-app project, which means that you can:**

* update `react-scripts`
* choose to remove some of the features I added

The [original CRA guidelines are still available here](README.cra.md)

## Prerequisites

* Nodejs v8
* npm v5

## Install

```shell
git clone https://github.com/topheman/my-react-app-starter.git
cd my-react-app-starter
npm install
```

## Run

```shell
npm start
```

## Build

```shell
npm run build
```

Will build a production version of the website in the `build` folder.

## Serve

Once you've built you're app, you can test the build on a local server with:

```shell
npm run serve
```

## Test

The following command will run all your tests in a single run mode.

```shell
npm test
```

### Unit

* `npm run test:unit` : single run of the unit tests
* `npm run test:unit:watch` : run the unit tests in watch mode

### End to end

No end to end test configured yet.

## Linter

I use eslint to check the coding style, with the following presets:

* [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb): An advanced set of eslint rules for JavaScript and React made by Airbnb
* [eslint-config-prettier](https://www.npmjs.com/package/eslint-config-prettier): Turns off all rules that are unnecessary or might conflict with Prettier.
* [eslint-config-react-app](https://www.npmjs.com/package/eslint-config-react-app): Shipping preset from create-react-app

The following command will run the linter on your code base. This task is ran at pre-commit to ensure code quality.

```shell
npm run lint
```

## Prettier

Prettier is a great tool to enforces a consistent style accross your code base (usefull when working in teams).

[Here is how to integrate it with your editor](https://prettier.io/docs/en/editors.html).

Once it's done, when you'll save a file, it will reformat it.

The following command will let you format your code base. This task is ran at pre-commit.

```shell
npm run pretty
```

## Deploy

The demo is hosted on [github-pages](https://topheman.github.io/my-react-app-starter). A simple way to publish your app is to use the [gh-pages](https://www.npmjs.com/package/gh-pages) package that will create a `gh-pages` orphan branch on which it will commit and push.

The following script will build then publish your app on your github pages:

```shell
npm run deploy
```

## Commit guidelines

To have uniform commit messages, I follow the [AngularJS git commit guidelines](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#-git-commit-guidelines), please take a look at it. I helps generate changelogs:

```shell
npm run generate-changelog -- v1.1.0 v1.2.0
```

Ready to be pasted to the github releases part.