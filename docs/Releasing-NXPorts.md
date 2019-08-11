# Releasing NXPorts

Releasing this package should always be a manual process. We might add more automation assistance in the future,
but in terms of generating official versions accessible through the public NuGet feed it should always be a
human element that initiates this process.

## Fundamentals

- We're releasing to production from `tag` builds
- We're releasing preview builds from `release/vX.XX.XX` branch builds
- We're not releasing anything from `master` branch builds

## Checklist

- [ ] Create `release/vNext` branch
- [ ] Verify correct version in [Global Properties](../Directory.Build.props) to `vNext`
- [ ] Verify that the [Changelog](../CHANGELOG.MD) does not contain any changes from `vCurrent`
- [ ] Check if all changes were listed in the [Changelog](../CHANGELOG.MD)
  - [ ] List all closed issues in this release
  - [ ] List all contributors who helped with this release
- [ ] Wait for all changes including documentation to be built
  - [ ] Automated tests succeed on all operating systems
  - [ ] Manual testing on the prerelease build
- [ ] Tag **HEAD** of `release/vNext` with vNext
- [ ] Move contents of the current [Changelog](../CHANGELOG.MD) to the [Release Notes Archive](./ReleaseNotes.md)
- [ ] Merge `release/vNext` into `master`
- [ ] Push `vNext` tag as well as `master` branch changes

## Glossary

- `vNext` -> Name of the version **to be released**
- `vCurrent` -> Name of the latest **released** Version