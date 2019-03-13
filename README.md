# @wiremore/grid

Simply put: it's a grid. A dead simple css grid with React components. Have a look at the Storybook for a preview: https://wiremore-grid.surge.sh/

## Installation

```sh
yarn add @wiremore/grid
```

or

```sh
npm install @wiremore/grid
```

## Usage

The grid has two named exports: `Grid` and `Column`. You can either import them from `@wiremore/grid/es` to import the pure ES modules or from `@wiremore/grid` to use the version that is pre-bundled as commonjs module with Webpack:

```jsx
import React from 'react';
import { Grid, Column } from '@wiremore/grid/es';

const Example = () => (
    <Grid>
        <Column xs={12} sm={6}>
            First Column
        </Column>
        <Column xs={12} sm={6}>
            Second Column
        </Column>
    </Grid>
);
```

## Contributing

This grid is developed using Storybook. Start storybook via `yarn start` or `npm start`. You can preview all your changes there.

### Commit messages

This project uses `semantic-release` and `semantic-release-conventional-commits` to automatically determine the next version number for new releases. By default every release is a patch release. Prefix your commit messages with `minor:` or `feature:` for new minor releases and `major:` or `breaking:` for new major releases. Have a look at [.releaserc](.releaserc) for more.

### Creating a new release

When you're done you need to publish your changes to the npm registry. First commit all your work (no need to create a build since semantic-release will take care of it in the release process). That's necessary so semantic-release can determine the next version number based on commit messages.

You need to setup your machine to allow semantic-release to push the new release to Github on your behalf. Follow this instruction: [Github Authentication](https://github.com/semantic-release/github/blob/master/README.md#github-authentication)

Once Github access is set up and after committing all your work, run:

```sh
yarn release
```

### Precommit checks

All updated files in `./src` are checked using ESLint and `lint-staged`. If there are linting errors your commit gets rejected. (You can bypass that check with the `--no-verify` flag but but I'd better not catch you doing it).
