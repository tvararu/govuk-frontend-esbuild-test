# govuk-frontend-esbuild-test

This is a repro repository for a bug.

`govuk-frontend@4.1.0` is currently failing to build with esbuild:

```sh
$ node -v
v18.1.0
$ yarn
yarn install v1.22.19
[1/5] Validating package.json...
[2/5] Resolving packages...
success Already up-to-date.
Done in 0.08s.
$ yarn build
yarn run v1.22.19
$ esbuild index.js --bundle
✘ [ERROR] Could not resolve "./common"
    node_modules/govuk-frontend/govuk-esm/all.mjs:1:32:
      1 │ import { nodeListForEach } from './common'
        ╵                                 ~~~~~~~~~~
✘ [ERROR] Could not resolve "./components/accordion/accordion"
    node_modules/govuk-frontend/govuk-esm/all.mjs:2:22:
      2 │ import Accordion from './components/accordion/accordion'
        ╵                       ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
✘ [ERROR] Could not resolve "./components/button/button"
    node_modules/govuk-frontend/govuk-esm/all.mjs:3:19:
      3 │ import Button from './components/button/button'
        ╵                    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
✘ [ERROR] Could not resolve "./components/details/details"
    node_modules/govuk-frontend/govuk-esm/all.mjs:4:20:
      4 │ import Details from './components/details/details'
        ╵                     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
✘ [ERROR] Could not resolve "./components/character-count/character-count"
    node_modules/govuk-frontend/govuk-esm/all.mjs:5:27:
      5 │ import CharacterCount from './components/character-count/character-count'
        ╵                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
✘ [ERROR] Could not resolve "./components/checkboxes/checkboxes"
    node_modules/govuk-frontend/govuk-esm/all.mjs:6:23:
      6 │ import Checkboxes from './components/checkboxes/checkboxes'
        ╵                        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
6 of 12 errors shown (disable the message limit with --log-limit=0)
node:child_process:855
    throw err;
    ^
Error: Command failed: /home/deity/git/govuk-frontend-esbuild-test/node_modules/esbuild-linux-64/bin/esbuild index.js --bundle
    at checkExecSyncError (node:child_process:817:11)
    at Object.execFileSync (node:child_process:852:15)
    at Object.<anonymous> (/home/deity/git/govuk-frontend-esbuild-test/node_modules/esbuild/bin/esbuild:172:28)
    at Module._compile (node:internal/modules/cjs/loader:1105:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1159:10)
    at Module.load (node:internal/modules/cjs/loader:981:32)
    at Module._load (node:internal/modules/cjs/loader:827:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:77:12)
    at node:internal/main/run_main_module:17:47 {
  status: 1,
  signal: null,
  output: [ null, null, null ],
  pid: 83518,
  stdout: null,
  stderr: null
}
Node.js v18.1.0
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
```

## Licence

Public domain.
