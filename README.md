# template-ts-package

Opinionated TypeScript template for new packages.

- [Source code](https://github.com/joaopalmeiro/template-ts-package)
- [npm package](https://www.npmjs.com/package/template-ts-package)
- [API](https://paka.dev/npm/template-ts-package@0.0.0/api)
- [Licenses](https://licenses.dev/npm/template-ts-package/0.0.0)

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

- Update the version in the `Licenses` and `API` links at the top.
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
