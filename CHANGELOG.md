# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added

### Changed

### Removed

## [0.9.7] - 2020-05-29
### Changed

 - Stop pruning `()` expressions in template position. [#174](https://github.com/jonhoo/inferno/pull/174)

## [0.9.6] - 2020-05-07
### Added

 - Support for combined event/stack lines. [#168](https://github.com/jonhoo/inferno/pull/168)

### Changed

 - Fix crash on empty traces. [#168](https://github.com/jonhoo/inferno/pull/168)
 - Also parse last sample in file. [#168](https://github.com/jonhoo/inferno/pull/168)

## [0.9.5] - 2020-03-18
### Added
- Add a new color option, color diffusion, that makes wider frames redder. This visually draws the eye towards places that need optimization. [#165](https://github.com/jonhoo/inferno/pull/165) by [@itamarst](https://github.com/itamarst).

## [0.9.4] - 2020-02-02
### Changed
- Fix bug where subtitles would often be hidden ([#161](https://github.com/jonhoo/inferno/pull/161) by [@itamarst](https://github.com/itamarst))

## [0.9.3] - 2020-02-02
### Added
- Overly long frame lanes can be shortened either on the left or the right ([#157](https://github.com/jonhoo/inferno/pull/157) by [@itamarst](https://github.com/itamarst))

### Changed
- By default, overly long frame lines are now shortened on the left ([#157](https://github.com/jonhoo/inferno/pull/157) by [@itamarst](https://github.com/itamarst))

## [0.9.2] - 2020-01-30
### Changed
- Replace `chashmap` with `dashmap` ([#155](https://github.com/jonhoo/inferno/pull/155) by [@koushiro](https://github.com/koushiro))
- Replace `fnv` with `ahash` ([#155](https://github.com/jonhoo/inferno/pull/155) by [@koushiro](https://github.com/koushiro))
- Update some outdated dependencies ([#155](https://github.com/jonhoo/inferno/pull/155) by [@koushiro](https://github.com/koushiro))
- Upgrade MSRV to 1.40.0 (required by `dashmap`) ([#155](https://github.com/jonhoo/inferno/pull/155) by [@koushiro](https://github.com/koushiro))

## [0.9.1] - 2019-10-31
### Added
- Support for collapsing the CSV output of the VTune `amplxe-cl` tool ([#148](https://github.com/jonhoo/inferno/pull/148) by [@jasonrhansen](https://github.com/jasonrhansen)).

### Changed
- The `sample` collapser now returns errors where it used to just log them in places where it doesn't make sense to continue.

## [0.9.0] - 2019-09-11
### Changed
- Support for multi-threaded collapsing was moved behind the
  `multithreaded` feature flag which is on by default ([#146](https://github.com/jonhoo/inferno/pull/146)).
- The `structopt` dependency has been updated, which bumps the minimum
  supported Rust version to 1.36.0 ([#145](https://github.com/jonhoo/inferno/pull/145)).
- Support for nameattr files was moved behind the `nameattr` feature
  flag which is on by default ([#147](https://github.com/jonhoo/inferno/pull/147)).

### Removed
- The `demangle` option for collapsers; we instead rely on the sample
  generator to demangle names, and then just do some post-processing
  fixups for common issues ([#144](https://github.com/jonhoo/inferno/pull/144)).
- The dependency on `rand`. Reduces the footprint of the crate, and also
  makes the random color choices seeded by the same number each run
  ([#146](https://github.com/jonhoo/inferno/pull/146)).

## [0.8.0] - 2019-07-24
### Added
- Changelog
- Support for collapsing the output of the `sample` tool on macOS ([#133](https://github.com/jonhoo/inferno/pull/133) by [@jasonrhansen](https://github.com/jasonrhansen)).
- Multi-core stack collapsing for _major_ speedups ([#128](https://github.com/jonhoo/inferno/pull/128) by [@bcmyers](https://github.com/bcmyers)).
- Support for "fluid drawing" of the SVG ([#136](https://github.com/jonhoo/inferno/pull/136) by [@jasonrhansen](https://github.com/jasonrhansen)).
- Make zoom and search part of browser history ([#121](https://github.com/jonhoo/inferno/pull/121) from [@AnderEnder](https://github.com/AnderEnder)).
  This is a backport of https://github.com/brendangregg/FlameGraph/pull/198 by [@versable](https://github.com/versable).
- The `--demangle` flag to collapsers for "re-doing" broken symbol demangling from DTrace or perf ([#132](https://github.com/jonhoo/inferno/pull/132) by [@jasonrhansen](https://github.com/jasonrhansen)).
- Unit tests for semantic coloring.
  JavaScript: [#129](https://github.com/jonhoo/inferno/pull/129) by [@jordins](https://github.com/jordins)
  Java: [#131](https://github.com/jonhoo/inferno/pull/131) by [@jkurian](https://github.com/jkurian)
- Cirrus CI for FreeBSD CI ([#124](https://github.com/jonhoo/inferno/pull/124) from [@AnderEnder](https://github.com/AnderEnder))

### Changed
- Moved to `IndexMap` and FNV hashing ([#127](https://github.com/jonhoo/inferno/pull/127))
- Moved CI to Azure DevOps Pipelines

[Unreleased]: https://github.com/jonhoo/inferno/compare/v0.9.7...HEAD
[0.9.7]: https://github.com/jonhoo/inferno/compare/v0.9.6...v0.9.7
[0.9.6]: https://github.com/jonhoo/inferno/compare/v0.9.5...v0.9.6
[0.9.5]: https://github.com/jonhoo/inferno/compare/v0.9.4...v0.9.5
[0.9.4]: https://github.com/jonhoo/inferno/compare/v0.9.3...v0.9.4
[0.9.3]: https://github.com/jonhoo/inferno/compare/v0.9.2...v0.9.3
[0.9.2]: https://github.com/jonhoo/inferno/compare/v0.9.1...v0.9.2
[0.9.1]: https://github.com/jonhoo/inferno/compare/v0.9.0...v0.9.1
[0.9.0]: https://github.com/jonhoo/inferno/compare/v0.8.0...v0.9.0
[0.8.0]: https://github.com/jonhoo/inferno/compare/v0.7.0...v0.8.0
