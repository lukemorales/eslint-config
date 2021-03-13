# Eslint and Prettier Setup
These are my settings for ESLint and Prettier

## What it does
* Lints Typescript based on the latest standards
* Fixes issues and formatting errors with Prettier
* Lints + Fixes React via eslint-config-airbnb
* You can see all the [rules here](https://github.com/lukemorales/eslint-config-lukemorales/blob/master/.eslintrc.json).

## Installing

1. Use the following command to install all the necessary deps **(remove the -Y if you don't use Yarn)**:

```
npx install-peerdeps --dev @lukemorales/eslint-config -Y
```

2. You can see in your package.json there are now a big list of devDependencies.

3. Add the following code to your `package.json`:

```json
"eslintConfig": {
   "extends": [
      "@lukemorales"
   ],
},
```

You can alternatively create a `.eslintrc` file in the root of your project's directory (it should live where package.json does). Your `.eslintrc` file should look like this:

```json
{
  "extends": [
    "@lukemorales"
  ],
}
```

4. You can add two scripts to your package.json to lint and/or fix:

```json
"scripts": {
  "lint": "eslint .",
  "lint:fix": "eslint . --fix"
},
```

5. Now you can manually lint your code by running `npm run lint` and fix all fixable issues with `npm run lint:fix`. You probably want your editor to do this though.

## Settings

If you'd like to overwrite eslint or prettier settings, you can add the rules in your `.eslintrc` file. The [ESLint rules](https://eslint.org/docs/rules/) go directly under `"rules"` while [prettier options](https://prettier.io/docs/en/options.html) go under `"prettier/prettier"`. Note that prettier rules overwrite anything in my config (trailing comma, and single quote), so you'll need to include those as well.

```js
{
  "extends": [
    "@lukemorales"
  ],
  "rules": {
    "no-console": "off"
  }
}
```

## With Create React App

1. Run `npx install-peerdeps --dev @lukemorales/eslint-config`
1. Crack open your `package.json` and replace `"extends": "react-app"` with `"extends": "@lukemorales"`
