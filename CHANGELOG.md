# 3.0.0

_Fixes and enhancements:_

- Replaced PhantomJS with Puppeteer
- Updated the config handling system to optionally load JSON files, and improved environment var loading
- Rewrote the HC caching system: it's now easier to include custom modules/depdencey lists in your own deployments
- The install step no longer requires interaction when installing
- Replaced the worker pool system with `generic-pool`
- Error messages are now sent back to the client instead of being displayed in rasterized output
- Updated NPM dependencies

_New Features:_

- Added `/health` route to server to display basic server information
- Added a UI served on `/` to perform exports from JSON configurations in browser

# 2.1.0

This version is not backwards compatible out of the box!

_Breaking changes:_

- Log destinations must now exist before starting file logging
- When running in server mode, the following options are now disabled by default:
  - `callback`
  - `resources`
  - `customCode`

Disabled options can be enabled by adding the `--allowCodeExecution` flag when
starting the server. Using this flag is not recommended, and should not be
done unless the server is sandboxed and not reachable on the public internet.

_Changelog_

- Added the `--allowCodeExecution` flag which is now required to be set when exporting pure JavaScript, using additional external resources, or using callback when running in server mode.
- Removed the `mkdirp` dependency
- SVG exporting will now block JavaScript entirely
- Added the `navigationLocked` flag to the Phantom page, which blocks e.g. `<iframe>` and page redirects.

# 2.0.30

- Fixed compatibility with `mkdirp >=v1.0`

# 2.0.29

- Added polyfill for `DOMParser` to accommodate Highcharts 9.0
- Updated some dependencies

# 2.0.28

- Fixed UUID and mkdirp versions in package.json

# 2.0.27

- Added `venn` module to build script

# 2.0.26

- Added `coloraxis` module to build script

# 2.0.25

- Fixed issue with optional scripts when using env variables to accept prompts

# 2.0.23

- Fixed issue with optional dependencies when installing headless

# 2.0.20-2.0.22

- Fixed pathing issue with NPM build when installing globally

# 2.0.19

- Added support for fetching sources through `npm` for automated builds. To use, set `HIGHCHARTS_CDN` to `npm`.
- Added support for `pareto` charts
- Fixed issue with script concatination causing exporting errors when including certain modules

# 2.0.18

- Added HIGHCHARTS_CDN variable support for build process

# 2.0.17

- Added support for 7.1 charts
- Updated dependencies

# 2.0.16

- Added support for bullet charts
- Added support for Gantt charts
- Added configuration option for chart generation timeout (`--timeoutThreshold`)
- Gracefull failing of 404 map collections now working properly
- Increased max configuration size from 5MB to 50MB
- Updated express version
- Updated docs

# 2.0.15

- Added `queueSize` option to `initPool` to set the request overfow queue size
- Added option to supply `cdnURL` to build script (#133)
- Added `;` between included scripts. Fixes map collections (#128)
- Added `--skipKey` and `--skipToken` CLI options to configure the rate limiter
- Added `--queueSize` switch to the CLI options to set the overflow queue size
- Fixed issue with silent installs and default values

# 2.0.14

- Fixed issue with CDN pull failing when using Highcharts < 6.0

# 2.0.13

- Fixed an issue that caused a comma to appear when exporting charts

# 2.0.12

- Build.js now uses cached respones when building styled mode to speed things up
- `historgram-bellcurve` is now included by default
- Added optional inclusion system to build.js
  - Will now prompt for inclusion of `wordcloud` and `annotations`

# 2.0.11

- Fixed another issue with `globalOptions` in CLI/Server mode

# 2.0.10

- Fixed issue with injecting some resources when they weren't strings (e.g. `globalOptions`)

# 2.0.9

- Added build config for including moment.js support

# 2.0.8

- Fixed `tmpdir` when starting in server mode

# 2.0.7

- Now including sunburst/xrange/streamgraph/tilemap when baking with a supported version
- Added package-lock.json

# 2.0.6

- Fixed issue potentially causing SVG exports to hang

# 2.0.5

- Increased timeout for rendering by 1 second
- Fixed port numbers for stress test

# 2.0.4

- Fixed bug causing unpredictable export results if one or more exported
  charts contain bundled images

# 2.0.3

- Server will now wait for bundled images to load

# 2.0.2

- Server now respects `host` option
- Added promise sample/test for batch export

# 2.0.1

- Fixed `tmpdir` when running as server

# 2.0.0

- Fixed Phantom cleanup: instead of reaping every 2.5s, workers are checked for timeout when other work is posted.
- Added additional error handlers to
  - `hhtp(s)Server`, `process`
- Worker busy check before restarting
- Now checking if the client connection is still open before sending returns
- Changed return codes for error conditions
- Misc stability fixes

# 1.0.15

- Fixed an issue with SVG export

# 1.0.12

- Fixed an issue with `--batch` exporting

# 1.0.11

- Fixed an issue with `themeOptions` when using CLI mode
- Added `listenToProcessExits` option to pool.init(..)
- Exposed `listenToProcessExits` in CLI mode
- Fixed issue with `--callback` when the callback was a file

# 1.0.10

- Fixed an issue with batch exporting
- Fixed `uuid` dependency version (thanks to @tonylukasavage)

# 1.0.9

- Set minimum node version to 5.10.0

# 1.0.8

- Fixed `phantomjs-prebuilt` dependency version
