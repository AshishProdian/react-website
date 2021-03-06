2.0.5 / 06.02.2018
==================

  * Fixed `@preload()`'s `blockingSibling` not being `true` by default.

2.0.4 / 05.02.2018
==================

  * Fixed `@preload()`s not being `blocking: true` by default.

2.0.3 / 26.01.2018
==================

  * Removed deprecated underscored configuration option names: `body_start`, `body_end`.
  * Removed the unused `beforeRender()` server-side configuration parameter. Can be added back upon request.
  * Server-side `render()` function: it now takes 4 arguments instead of 2. And the object being returned also changed. See README-ADVANCED for more info.
  * Now also exporting `renderError(error, options)` which can be used in pair with the exported `render()` server-side function. See README-ADVANCED for more info.

2.0.0 / 28.12.2017
==================

  * (could possibly be a breaking change for someone, but that's unlikely) Asynchronous middleware `action.result` property of "success" action renamed to `action.value`.

  * (breaking change) `result` parameter of Redux module has been moved from `options` argument to an argument itself. Migration guide: `reduxModule.action(event, action, { result })` -> `reduxModule.action(event, action, result, options = {})`.

  * (breaking change) Redux module synchronous actions' `result` is now `(state, result) => ...` instead of `(state, action) => ...` where `result` is what's being returned from `action`.

  * Synchronous action `payload()` parameter of Redux module has been renamed to `action()` along with passing `sync: true` flag: `reduxModule.action(event, { payload, result })` -> `reduxModule.action(event, action, result, { sync: true })`. The old name still works but is deprecated.

1.0.0 / 19.12.2017
==================

  * (breaking change) Renamed `react-isomorphic-render` to `react-website` since the project outgrew its initial name and it's now more about building a React application rather than just isomorphic React rendering.
  * (breaking change) Dropped old React support, now supports React >= 16 only.
  * (breaking change) Removed `koa` entirely (for simplicity).
  * (breaking change) Added `secure` flag to page rendering service options for HTTPS.
  * (breaking change) `wrapper` parameter renamed to `container`.
  * (breaking change) `preload` reducer is now added by default and "preload" reducer name is now reserved for it. `<Loading/>` component is also now built-in into the library and can be `import`ed from it.
  * (breaking change) Removed `request` from rendering service `initialize()` parameters (may be added back, upon request).
  * (breaking change) Removed `loading` from rendering service parameters (seems that it was never used).
  * (breaking change) `render: false` parameter renamed to `hollow: true`.
  * `reduxEventNaming` and `reduxPropertyNaming` are now set by default.
  * (breaking change) `@preload()` now doesn't automatically convert `Array`s into `Promise.all(array)`.
  * (breaking change) `@preload()` `helpers` removed (may be added back upon request).
  * (breaking change) Removed `{ preload: { client } }` configuration parameter.
