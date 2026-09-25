# template-ts-package

Opinionated TypeScript template for new packages.

- [Source code](https://github.com/joaopalmeiro/template-ts-package)
- [npm](https://www.npmjs.com/package/template-ts-package)
- [npmx](https://npmx.dev/package/template-ts-package)

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
9. Update the `homepage`, `bugs.url`, and `repository.url` fields in the `package.json` file with their respective repository-related links (if necessary).
10. Delete the [deprecated/](deprecated) folder and the corresponding configuration in the [.vscode/settings.json](.vscode/settings.json) and [.oxlintrc.json](.oxlintrc.json) files.
11. Remove `template-tsdown/` from the [.gitignore](.gitignore) file.
12. Delete the [TEMPLATE.md](TEMPLATE.md) file.
13. Delete the [`Getting Started`](#getting-started) section.

## Development

Install [zizmor](https://docs.zizmor.sh/installation/) and [pinact](https://github.com/suzuki-shunsuke/pinact/blob/main/INSTALL.md) (if necessary).

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

```bash
npm pack --dry-run
```

### GitHub Actions

```bash
zizmor .
```

```bash
pinact run -u --min-age 7
```

## Deployment

- Create the `release` [GitHub Actions environment](https://github.com/joaopalmeiro/template-ts-package/settings/environments) (if necessary).
- [Configure trusted publishing](https://docs.npmjs.com/trusted-publishers#configuring-trusted-publishing) (if necessary).

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
- Check GitHub: [Tags](https://github.com/joaopalmeiro/template-ts-package/tags) and [Actions](https://github.com/joaopalmeiro/template-ts-package/actions).
- Check [npm](https://www.npmjs.com/package/template-ts-package).
