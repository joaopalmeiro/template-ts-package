# template-ts-package

Opinionated TypeScript template for new packages.

- [Source code](https://github.com/joaopalmeiro/template-ts-package)
- [npm package](https://www.npmjs.com/package/template-ts-package)
- [API](https://paka.dev/npm/template-ts-package@0.0.0/api)
- [Licenses](https://licenses.dev/npm/template-ts-package/0.0.0)

## Getting Started

1. Go to or create the package folder.
2. Get the template files:

```bash
npx degit github:joaopalmeiro/template-ts-package
```

or

```bash
npx degit github:joaopalmeiro/template-ts-package --force
```

3. Search for `template-ts-package` and replace it with the package name.
4. Search for `Opinionated TypeScript template for new packages.` and replace it with the (short) package description.
5. Search for `João Palmeiro` and replace it with the author's name.
6. Search for `jm.palmeiro@campus.fct.unl.pt` and replace it with the author's email address.
7. Change the `author.url` field in the `package.json` file to the author's website/social media profile.
8. Install [fnm](https://github.com/Schniz/fnm) (if necessary).
9. Run the first two commands in the [`Development` section](#development) to install [Node.js](https://nodejs.org/en) and the development dependencies.
10. Open the [NOTES.md](NOTES.md) file and install the package-specific dependencies according to the first command in the [Commands section](NOTES.md#commands).
11. Update the `Source code` link at the top to the package repository link (if necessary).
12. Change `GitHub` in the [`Deployment` section](#deployment) to `GitLab` or `Codeberg` and update the link to the corresponding Tags page (if necessary).
13. Update the `homepage`, `bugs.url`, and `repository.url` fields in the `package.json` file with their respective repository-related links (if necessary).
14. Delete the [TEMPLATE.md](TEMPLATE.md) file.
15. Delete the [`Getting Started` section](#getting-started).

## Development

Install [fnm](https://github.com/Schniz/fnm) (if necessary).

```bash
fnm install && fnm use && node --version && npm --version
```

```bash
npm install
```

```bash
npm run lint
```

```bash
npm run format
```

```bash
npm run build
```

## Deployment

```bash
npm pack --dry-run
```

```bash
npm version patch
```

```bash
npm version minor
```

```bash
npm version major
```

- Update the version in the `API` and `Licenses` links at the top.
- Commit and push changes.
- Create a tag on [GitHub Desktop](https://github.blog/2020-05-12-create-and-push-tags-in-the-latest-github-desktop-2-5-release/).
- Check [GitHub](https://github.com/joaopalmeiro/template-ts-package/tags).

```bash
npm login
```

```bash
npm publish
```

- Check [npm](https://www.npmjs.com/package/template-ts-package).
