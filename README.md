# template-ts-package

Opinionated TypeScript template for new packages.

- [Source code](https://github.com/joaopalmeiro/template-ts-package)
- [npm package](https://www.npmjs.com/package/template-ts-package)
- [bundlejs](https://bundlejs.com/?bundle&q=template-ts-package)
- [Licenses](https://licenses.dev/npm/template-ts-package)
- [Node Modules Inspector](https://node-modules.dev/report#install=template-ts-package)
- [npm trends](https://npmtrends.com/template-ts-package)
- [npmgraph.an](https://npm.anvaka.com/#/view/2d/template-ts-package)
- [npmgraph](https://npmgraph.js.org/?q=template-ts-package)
- [npmx](https://npmx.dev/package/template-ts-package)
- [Package Phobia](https://packagephobia.com/result?p=template-ts-package)
- [Snyk](https://security.snyk.io/package/npm/template-ts-package)

## Getting Started

1. Go to or create the package folder.
2. Get the template files:

```bash
npx giget github:joaopalmeiro/template-ts-package . --force
```

3. Search for `template-ts-package` and replace it with the package name. Ignore the template repository URL in the [NOTES.md](NOTES.md) file.
4. Search for `Opinionated TypeScript template for new packages.` and replace it with the (short) package description.
5. Search for `João Palmeiro` and replace it with the author's name.
6. Search for `joaopalmeiro@proton.me` and replace it with the author's email address.
7. Change the `author.url` field in the `package.json` file to the author's website/social media profile.
8. Install [fnm](https://github.com/Schniz/fnm) (if necessary).
9. Update the `Source code` link at the top to the package repository link (if necessary).
10. Change `GitHub` in the [`Deployment`](#deployment) section to `GitLab` or `Codeberg` and update the link to the corresponding Tags page (if necessary).
11. Update the `homepage`, `bugs.url`, and `repository.url` fields in the `package.json` file with their respective repository-related links (if necessary).
12. Delete the [deprecated/](deprecated) folder and the corresponding configuration in the [.vscode/settings.json](.vscode/settings.json) and [.oxlintrc.json](.oxlintrc.json) files.
13. Remove `template-tsdown/` from the [.gitignore](.gitignore) file.
14. Delete the [TEMPLATE.md](TEMPLATE.md) file.
15. Delete the [`Getting Started`](#getting-started) section.

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

```bash
echo "v$(npm pkg get version | tr -d \")" | pbcopy
```

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
