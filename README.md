# Steps

1. Init repo

```bash
pnpm create vuepress-theme-hope SymbolNotFound
```

2. Update dependencies (vue 3.2.47 -> 3.3.1)

```bash
pnpm docs:update-package
```

3. Use autocatalog ([src/guide/README.md](src/guide/README.md))

```md
---
title: Guide
icon: creative
---

<AutoCatalog />
```

Now the build will fail with the following error (while dev preview will not raise such error as it is not in production mode):

```
[Vue warn]: injection "Symbol()" not found.
[Vue warn]: Unhandled error during execution of render function
  at <AutoCatalog >
✖ Rendering 25 pages - failed in 201ms
TypeError: Cannot read properties of undefined (reading 'getRoutes')
    at E2 (file:///path/to/SymbolNotFound/src/.vuepress/.temp/.server/app.e3a951d3.mjs:5109:75)
    at ReactiveEffect.fn (file:///path/to/SymbolNotFound/src/.vuepress/.temp/.server/app.e3a951d3.mjs:5143:26)
    at ReactiveEffect.run (/path/to/SymbolNotFound/node_modules/.pnpm/@vue+reactivity@3.3.1/node_modules/@vue/reactivity/dist/reactivity.cjs.js:162:19)
    at get value [as value] (/path/to/SymbolNotFound/node_modules/.pnpm/@vue+reactivity@3.3.1/node_modules/@vue/reactivity/dist/reactivity.cjs.js:1143:33)
    at Proxy.<anonymous> (file:///path/to/SymbolNotFound/src/.vuepress/.temp/.server/app.e3a951d3.mjs:5144:118)
    at renderComponentRoot (/path/to/SymbolNotFound/node_modules/.pnpm/@vue+runtime-core@3.3.1/node_modules/@vue/runtime-core/dist/runtime-core.cjs.js:812:16)
    at renderComponentSubTree (/path/to/SymbolNotFound/node_modules/.pnpm/@vue+server-renderer@3.3.1_vue@3.3.1/node_modules/@vue/server-renderer/dist/server-renderer.cjs.prod.js:440:28)
    at renderComponentVNode (/path/to/SymbolNotFound/node_modules/.pnpm/@vue+server-renderer@3.3.1_vue@3.3.1/node_modules/@vue/server-renderer/dist/server-renderer.cjs.prod.js:371:12)
    at renderVNode (/path/to/SymbolNotFound/node_modules/.pnpm/@vue+server-renderer@3.3.1_vue@3.3.1/node_modules/@vue/server-renderer/dist/server-renderer.cjs.prod.js:483:14)
    at renderComponentSubTree (/path/to/SymbolNotFound/node_modules/.pnpm/@vue+server-renderer@3.3.1_vue@3.3.1/node_modules/@vue/server-renderer/dist/server-renderer.cjs.prod.js:386:5)
 ELIFECYCLE  Command failed with exit code 1.
```
