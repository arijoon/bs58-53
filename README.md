# Reproducing a bs58 inport issue in typescript

[Issue](https://github.com/cryptocoinjs/bs58/issues/53) in bs58 repo

Reproduction command with `nix`:

```sh
> nix-shell --run 'pnpm tsc -b'
index.ts:1:18 - error TS1479: The current file is a CommonJS module whose imports will produce 'require' calls; however, the referenced file is an ECMAScript module and cannot be imported with 'require'. Consider writing a dynamic 'import("bs58")' call instead.
  To convert this file to an ECMAScript module, change its file extension to '.mts', or add the field `"type": "module"` to '/code/vendor/bs58-cjs-import/package.json'.

1 import bs58 from 'bs58'
                   ~~~~~~


Found 1 error.
```

Without nix, simply install `pnpm` and run `pnpm install && pnpm tsc -b`
