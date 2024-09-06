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

## Deprecated links

- [Types](https://tsdocs.dev/docs/template-ts-package/0.0.0)
- [API](https://paka.dev/npm/template-ts-package@0.0.0/api)
- [Licenses](https://licenses.dev/npm/template-ts-package/0.0.0)
- [Package Phobia](https://packagephobia.com/result?p=template-ts-package@0.0.0)
- [bundlejs](https://bundlejs.com/?bundle&q=template-ts-package%400.0.0)

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
