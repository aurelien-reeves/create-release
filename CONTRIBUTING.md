Everyone contributing to this repo is expected to abide by the [Cucumber Community Code of Conduct](https://cucumber.io/conduct).

## Making a release

There are two parts to making a release. First, prepare the release, then make the release.

### Preparing a release

Anyone with commit rights to `main` can prepare a release.

To make a release of this action, you can use the [`changelog`](https://github.com/rcmachado/changelog) tool.

First, make sure your changes are detailed in the `Unreleased` section of the [CHANGELOG](./CHANGELOG.md) file.

Then, use [semver](https://semver.org/) to pick a version for the next release.

    read $next_release

Modify the changelog:

    changelog release $next_release -o CHANGELOG.md

Commit and push

     git add .
     git commit -m "Release $next_release"

The [`pre-release` workflow](https://github.com/cucumber-actions/create-release/actions/workflows/pre-release.yaml) will pick up your changes and create a pull request for the release.

### Making a release

Only people with rights to push to the `release/*` branch pattern can make releases.
