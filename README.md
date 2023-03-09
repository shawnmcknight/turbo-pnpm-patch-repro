This repo provides a reproduction of turbo prune not applying pnpm patched dependencies properly. To reproduce:

- Clone the repo
- `pnpm install`
- `pnpm exec turbo prune --scope=test`

The `out` folder contents will not properly apply the patch:

- The `package.json` file will have `pnpm.patchedDependencies` as empty object
- The `pnpm-workspace.yaml` file will not have a property for `patchedDependencies`
- The `patches` folder will not be there
