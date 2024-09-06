# Template Notes

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

## Deprecated links

- [Types](https://tsdocs.dev/docs/template-ts-package/0.0.0)

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

### Minimal `.npmrc`

```ini
package-lock=false
save-exact=true
git-tag-version=false
engine-strict=true
```
