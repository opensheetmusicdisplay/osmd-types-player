# osmd-types-player
Type Definitions for the OSMD Audio Player

## How to use the types
* add osmd-types-player as a dependency in package.json:
```json
  "dependencies": {
    "osmd-types-player": "git+https://github.com/opensheetmusicdisplay/osmd-types-player.git#ff8081b60e32f80cb1d7a5746cfd0e66f769953e"
  }
```
(the hash at the end is the commit hash, so update this to use the latest commit)
* in `tsconfig.json`, add this:
```json
    "typeRoots": [
      "node_modules/@types",
      "node_modules/osmd-types-player",
    ],
```
* (optional) add `"opensheetmusicdisplay": "file:opensheetmusicdisplay.min.js"` as a dependency (this is the audio player build)
* npm install
* now you can import types, e.g.:
```js
import type { IOSMDOptions } from 'opensheetmusicdisplay';
import { PlaybackManager } from 'opensheetmusicdisplay';
```

## How to generate/update the types
* checkout the osmd audio player repository
* run `npm install` if necessary
* run `npm run build` if necessary (to get up to date type definitions)
* `npm i -g @microsoft/api-extractor`
* `api-extractor run --local --verbose`
* rolled up definitions will be in `build/dist/src/`

<details><summary>the alternative dts-bundle seems to create erroneous syntax</summary>

* checkout the osmd audio player repository
* run `npm install` if necessary
* run `npm run build` if necessary (to get up to date type definitions)
* run `npm install -g dts-bundle` if necessary (will install this package globally)
* `cd build/dist/src`
* `dts-bundle --name opensheetmusicdisplay --main .\index.d.ts`
* rolled up definitions will be in `build/dist/src/`
</details>
