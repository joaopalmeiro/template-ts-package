# Template Notes

- https://codeberg.org/joaopalmeiro/biome-config
- https://codeberg.org/joaopalmeiro/misc-tsconfigs
- https://github.com/uidotdev/npm-trends
- https://docs.npmjs.com/cli/v9/commands/npm-pkg
- https://uly.me/remove-quotes-from-strings
- https://github.com/github-linguist/linguist/blob/4ac734c15a96f9e16fd12330d0cb8de82274f700/lib/linguist/languages.yml#L1771
- Biome:
  - https://biomejs.dev/internals/changelog/
  - https://github.com/biomejs/biome/releases
  - https://github.com/biomejs/biome/blob/cli/v1.6.3/crates/biome_service/src/workspace.rs#L101
  - https://biomejs.dev/reference/cli/#biome-rage
  - https://biomejs.dev/linter/rules/use-sorted-classes/
- https://docs.npmjs.com/cli/v9/configuring-npm/npmrc: "All npm config files are an ini-formatted (...)"
- https://github.com/anvaka/npmgraph.an
- https://johnnyreilly.com/dual-publishing-esm-cjs-modules-with-tsup-and-are-the-types-wrong:
  - `"build": "tsup src/index.ts --format cjs,esm --dts --clean --sourcemap"`
- https://github.com/arethetypeswrong/arethetypeswrong.github.io/releases:
  - https://www.npmjs.com/package/@arethetypeswrong/cli/v/0.16.0
- https://www.warp.dev/terminus/clear-npm-cache
- https://www.totaltypescript.com/how-to-create-an-npm-package:
  - https://www.totaltypescript.com/how-to-create-an-npm-package#56-fix-the-cjs-warning:
    - "If you don't want to support CJS (which I recommend), change the check-exports script to: `{ "scripts": { "check-exports": "attw --pack . --ignore-rules=cjs-resolves-to-esm" } }`"
    - https://www.totaltypescript.com/tsconfig-cheat-sheet
    - https://github.com/total-typescript/tsconfig/blob/a42aef4f2350ac88b0b5d6ce88325481c964188d/bundler/no-dom.json
    - https://github.com/total-typescript/tsconfig/blob/a42aef4f2350ac88b0b5d6ce88325481c964188d/tsc/no-dom/library.json
- https://github.com/mattpocock/package-tools
- https://github.com/egoist/tsup/blob/v8.2.4/src/options.ts#L191-L195
- https://github.com/mikaelbr/marked-terminal: "A custom render for marked to output to the Terminal"
- https://github.com/egoist/tsup/releases
- https://github.com/bluwy/publint/releases
- https://publint.dev/rules#invalid_repository_value
- https://semver.npmjs.com/#syntax-examples:
  - https://semver.npmjs.com/
  - `>=1.0.0-rc.0 <1.0.1`
  - SVGO: `>=4.0.0-rc.0`
- TanStack Config:
  - https://tanstack.com/config/latest
  - https://tanstack.com/config/latest/docs/publish
  - https://github.com/TanStack/config
- https://github.com/icelib/npm-lib-template
- https://tsdown.dev/guide/
- https://tsdown.dev/options/lint
- https://tsdown.dev/reference/api/Interface.DtsOptions#tsgo
- https://tsdown.dev/options/dts#declaration-map + https://tsdown.dev/options/sourcemap
- https://github.com/lirantal/npm-security-best-practices
- https://github.com/actions/setup-node
- Trusted publishing:
  - https://docs.npmjs.com/trusted-publishers
  - https://docs.github.com/en/actions/how-tos/deploy/configure-and-manage-deployments/manage-environments
  - https://github.com/feedzai/AutoVizuA11y/blob/b819e1e45a0c2958db56f934aa1c6de313ca4a2d/.github/workflows/release_package.yml
- https://github.com/ai/clean-npm-project
- https://github.com/shashkovdanil/clean-publish
- https://github.com/step-security/harden-runner

## Deprecated links

- [Types](https://tsdocs.dev/docs/template-ts-package/0.0.0)
- [API](https://paka.dev/npm/template-ts-package@0.0.0/api)
- [Licenses](https://licenses.dev/npm/template-ts-package/0.0.0)
- [Package Phobia](https://packagephobia.com/result?p=template-ts-package@0.0.0)
- [bundlejs](https://bundlejs.com/?bundle&q=template-ts-package%400.0.0)

## Commands

```bash
npm create tsdown@0.23.0 template-tsdown
```

```bash
npm install -D "@types/node@$(cat .nvmrc | cut -d . -f 1-2)"
```

```bash
npx clean-publish --without-publish
```

## Snippets

```markdown
14. Delete the [`Template References` section](NOTES.md#template-references) from the [NOTES.md](NOTES.md) file.
```

```ini
root = true

[*]
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
charset = utf-8

# Source:
# - https://biomejs.dev/guides/how-biome-works/#protected-files
# - https://github.com/biomejs/biome/blob/cli/v1.5.3/crates/biome_service/src/workspace.rs#L100
# To ensure consistent indent size with Biome (package.json and tsconfig.json are ignored by Biome):
[{package.json,tsconfig.json}]
indent_size = 2
```

```markdown
- Update the version in the `API`, `Licenses`, `Package Phobia`, and `bundlejs` links at the top.
```

### Minimal `.npmrc`

```ini
package-lock=false
save-exact=true
git-tag-version=false
engine-strict=true
```

- https://johnnyreilly.com/dual-publishing-esm-cjs-modules-with-tsup-and-are-the-types-wrong

```json
{
  "//": "This is the correct way to set up a package with a `src/index.ts` root file that supports both ESM and CJS modules.",
  "type": "module",
  "main": "./dist/index.cjs",
  "module": "./dist/index.js",
  "types": "./dist/index.d.ts",
  "exports": {
    "import": {
      "types": "./dist/index.d.ts",
      "import": "./dist/index.js"
    },
    "require": {
      "types": "./dist/index.d.cts",
      "require": "./dist/index.cjs"
    }
  }
}
```

- https://github.com/mattpocock/tt-package-demo/blob/83de5832841954a26eca84331f5e403051f0e755/tsup.config.ts

```ts
import { defineConfig } from "tsup";

export default defineConfig({
  entryPoints: ["src/index.ts"],
  format: ["cjs", "esm"],
  dts: true,
  outDir: "dist",
  clean: true,
});
```

- https://github.com/icelib/npm-lib-template/blob/759dee7863873a7f147ae845157af38736d39a66/tsdown.config.ts

```ts
import { defineConfig } from "tsdown";

export default defineConfig({
  entry: ["src/index.ts"],
  format: ["esm", "cjs"],
  dts: true,
  clean: true,
});
```

- https://github.com/ai/multiocular/blob/0cde4c8fe349b590c6845ae9b2767ae40b896d3c/.github/workflows/publish.yml

```yml
name: Publish
on:
  push:
    tags:
      - "*"
jobs:
  test:
    name: Run Tests
    uses: ./.github/workflows/test.yml
  build:
    name: Build JS safer
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - name: Harden the runner
        uses: step-security/harden-runner@bf7454d06d71f1098171f2acdf0cd4708d7b5920 # v2.20.0
        with:
          egress-policy: block
          allowed-endpoints: >
            api.github.com:443
            github.com:443
            nodejs.org:443
            release-assets.githubusercontent.com:443
            objects.githubusercontent.com:443
            registry.npmjs.org:443
      - name: Checkout the repository
        uses: actions/checkout@9c091bb21b7c1c1d1991bb908d89e4e9dddfe3e0 # v7.0.0
      - name: Install Node.js & pnpm
        uses: pnpm/setup@5d160c5bc68a09337ad0d5654e237e03253b5879 # v1.0.0
        with:
          version: 11
          runtime: node@26
      - name: Install dependencies
        run: pnpm install --ignore-scripts
      - name: Run build
        run: pnpm build
      - name: Upload build artifacts
        uses: actions/upload-artifact@043fb46d1a93c77aae656e7c1c64a875d1fc6a0a # v7.0.1
        with:
          name: build-artifacts
          path: dist/
          retention-days: 1
  publish:
    name: Publish to npm
    needs:
      - test
      - build
    runs-on: ubuntu-latest
    permissions:
      contents: read
      id-token: write
    steps:
      - name: Harden the runner
        uses: step-security/harden-runner@bf7454d06d71f1098171f2acdf0cd4708d7b5920 # v2.20.0
        with:
          egress-policy: block
          allowed-endpoints: >
            api.github.com:443
            github.com:443
            release-assets.githubusercontent.com:443
            registry.npmjs.org:443
            *.sigstore.dev:443
      - name: Checkout the repository
        uses: actions/checkout@9c091bb21b7c1c1d1991bb908d89e4e9dddfe3e0 # v7.0.0
      - name: Download build artifacts
        uses: actions/download-artifact@3e5f45b2cfb9172054b4087a40e8e0b5a5461e7c # v8.0.1
        with:
          name: build-artifacts
          path: dist/
      - name: Install npm
        uses: actions/setup-node@820762786026740c76f36085b0efc47a31fe5020 # v7.0.0
        with:
          node-version: 26
          registry-url: "https://registry.npmjs.org"
      - name: Publish to npm with provenance
        run: cd dist && npm stage publish --provenance --access public
  release:
    name: Create GitHub Release
    needs: test
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - name: Harden the runner
        uses: step-security/harden-runner@bf7454d06d71f1098171f2acdf0cd4708d7b5920 # v2.20.0
        with:
          egress-policy: block
          allowed-endpoints: >
            api.github.com:443
            github.com:443
      - name: Checkout the repository
        uses: actions/checkout@9c091bb21b7c1c1d1991bb908d89e4e9dddfe3e0 # v7.0.0
      - name: Clean npm package
        uses: ai/copy-changelog-to-release@a6dc825c34575add2da2060796794f7b84894628 # v0.2.0
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

- https://github.com/ai/nanospy/blob/d8f30882babe8baf41add90411bb989a1403003b/.github/workflows/release.yml

```yml
name: Release
on:
  push:
    tags:
      - "*"
jobs:
  publish:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      id-token: write
    steps:
      - name: Checkout the repository
        uses: actions/checkout@9c091bb21b7c1c1d1991bb908d89e4e9dddfe3e0 # v7.0.0
        with:
          persist-credentials: false
      - name: Clean npm package
        uses: ai/clean-npm-project@0e1fd6e68c39b972235226864d47e368c550ebed # v0.2.3
        with:
          clean-docs: true
      - name: Install Node.js
        uses: actions/setup-node@48b55a011bda9f5d6aeb4c2d9c7362e8dae4041e # v6.4.0
        with:
          node-version: 26
      - name: Publish npm package
        run: npm stage publish
        working-directory: cleaned-project/
  release:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - name: Checkout the repository
        uses: actions/checkout@9c091bb21b7c1c1d1991bb908d89e4e9dddfe3e0 # v7.0.0
        with:
          persist-credentials: false
      - name: Clean npm package
        uses: ai/copy-changelog-to-release@d5918dc4898c6edab80133cea308047acf28805e # v0.1.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
