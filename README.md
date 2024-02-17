# osmd-types-player
Type Definitions for the OSMD Audio Player

## How to use the types
* add osmd-types-player as a dependency in package.json
* add `"opensheetmusicdisplay": "file:opensheetmusicdisplay.min.js"` as a dependency (this is the audio player build)
* npm install
* in `tsconfig.json`, add this:
```json
    "typeRoots": [
      "node_modules/@types",
      "node_modules/osmd-types-player",
    ],
```
* now you can import types, e.g.:
```js
import type { IOSMDOptions } from 'opensheetmusicdisplay';
import { PlaybackManager } from 'opensheetmusicdisplay';
```

## How to generate/update the types
* checkout the osmd audio player repository
* run `npm install` if necessary
* run `npm run build` if necessary
* run `npm install -g dts-bundle` if necessary (will install this package globally)
* `cd build/dist/src`
* `dts-bundle --name opensheetmusicdisplay --main .\index.d.ts`
