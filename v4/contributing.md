# Contributing

To contribute just create a pull request and describe the changes.

## Running locally

1. Clone the repository and install the dependencies with `npm install`.
2. Use `ng serve` (v4) or `ionic serve` (v3) to run the app that contains Ionic Selectable module together with demos.

## Prepare release

1. Update the version in the `package.json` according to [Semantic Versioning](https://semver.org/). For example, if the release contains breaking changes than major number should be bumped and others reset to 0 - from `4.1.6` to `5.0.0`.
2. Run `gulp` from the root folder to prepare an npm package that will be created in `dist` folder.
3. Run `npm publish dist` to publish the package to npm.
4. Create a GitHub tag and describe the changes following the [pattern](https://github.com/ionic-selectable/ionic-selectable/releases/tag/4.2.0).

## Conventions

### Naming

1. **Boolean** fields and variables should start with `is`, `has`, `can`, `should`, etc, for example `isDisabled`, `hasConfirmButton`, `canSearch`, `shouldFocusSearchbar`.
2. **Events** should be named using continuous or past participle form, for example **searching**, **changed**, **selected**, **itemAdded**. This will allow to differentiate between starting and ending events, for example, `opening` and `opened`. In some cases a starting event might be cancelled, where an ending event have already completed. For instance, cancellation can be implemented for `opening` even to prevent it based on some conditions.
3. Prefer complete words over contractions, for example, `element` instead of `el`, `event` instead of `ev`, `count` instead of `cnt`, etc. Some commonly used contractions are allowed: `id`, `min`, `max`.
4. Avoid general suffixes that don't add value to the meaning, such as `Detail`, `Details`, `Data`, etc. For example, prefer `Item` over `ItemDetail`.
5. Add `I` prefix to interfaces. It might seem an obsolete `Hungarian notation`, but it allows to have consistent short names for both class and its interface. For example, `interface IEvent` and `class Event implements IEvent`.

### Formatting

1. Use [Prettier](https://prettier.io/) code formatter. Rules are set up in `.prettierrc` file.
2. Install and use [editorconfig](https://editorconfig.org/) extension for your IDE. Rules are set up in `.editorconfig` file.

### Git

1. A commit message should represent a complete sentence starting with a capital letter and ending with a dot, for example, `Added isDisabled field.`. A prefix can be added where applicable to label the commit.
   Some common prefixes:

- **Issue** prefix, for example, `#22: Added isDisabled field.`
