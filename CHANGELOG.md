# Changelog

All notable changes to this project will be documented in this file. (Hopefully.)

## [Unreleased]

## [1.0.1] - in progress

Made changes to support newer macOS versions from around 2020 and later.

### Changed

- Switch to three-part "X.Y.Z" SemVer style versioning.
- Switch from Python 2 to Python 3, to support macOS 12.3 and newer, which removed Python 2.
  - On macOS versions before macOS 13, may require installing Python 3.
- Make `--no-internet-enable` the default, since hdiutil internet-enable seems to have disappeared as of macOS 12 or so.

## [1.0.0.1]

The published version that existed as of 2020. We don't have changelog notes prior to that.
