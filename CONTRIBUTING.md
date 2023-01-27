# Contributing to GoWSL

A big welcome and thank you for considering contributing to GoWSL and Ubuntu! It’s people like you that make it a reality for users in our community.

Reading and following these guidelines will help us make the contribution process easy and effective for everyone involved. It also communicates that you agree to respect the time of the developers managing and developing this project. In return, we will reciprocate that respect by addressing your issue, assessing changes, and helping you finalize your pull requests.

These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

## Quicklinks

* [Code of Conduct](#code-of-conduct)
* [Getting Started](#getting-started)
* [Issues](#issues)
* [Pull Requests](#pull-requests)
* [Contributing to the code](#contributing-to-the-code)
* [Contributor Licence Agreement](#contributor-license-agreement)
* [Getting Help](#getting-help)

## Code of Conduct

We take our community seriously and hold ourselves and other contributors to high standards of communication. By participating and contributing to this project, you agree to uphold our [Code of Conduct](https://ubuntu.com/community/code-of-conduct).

## Getting Started

Contributions are made to this project via Issues and Pull Requests (PRs). A few general guidelines that cover both:

* To report security vulnerabilities, please use the advisories page of the repository and not a public bug report.
* Search for existing Issues and PRs before creating your own.
* We work hard to make sure issues are handled promptly but, depending on the impact, it could take a while to investigate the root cause. A friendly ping in the comment thread to the submitter or a contributor can help draw attention if your issue is blocking.
* If you've never contributed before, see [this Ubuntu discourse post](https://discourse.ubuntu.com/t/contribute/26) for resources and tips on how to get started.

### Issues

Issues should be used to report problems with the software, request a new feature, or discuss potential changes before a PR is created. When you create a new Issue, a template will be loaded that will guide you through collecting and providing the information we need to investigate.

If you find an Issue that addresses the problem you're having, please add your reproduction information to the existing issue rather than creating a new one. Adding a [reaction](https://github.blog/2016-03-10-add-reactions-to-pull-requests-issues-and-comments/) can also help be indicating to our maintainers that a particular problem is affecting more than just the reporter.

### Pull Requests

PRs to our project are always welcome and can be a quick way to get your fix or improvement slated for the next release. In general, PRs should:

* Only fix/add the functionality in question **OR** address widespread whitespace/style issues, not both.
* Add unit or integration tests for fixed or changed functionality.
* Address a single concern in the least number of changed lines as possible.
* Include documentation in the repository.
* Be accompanied by a complete Pull Request template (loaded automatically when a PR is created).

For changes that address core functionality or would require breaking changes (e.g. a major release), it's best to open an Issue to discuss your proposal first. This is not required but can save time in creating and reviewing changes.

In general, we follow the ["fork-and-pull" Git workflow](https://github.com/susam/gitpr)

1. Fork the repository to your own GitHub account
1. Clone the project to your machine
1. Create a branch locally with a succinct but descriptive name
1. Commit changes to the branch
1. Following any formatting and testing guidelines specific to this repo
1. Push changes to your fork
1. Open a PR in our repository and follow the PR template so that we can efficiently review the changes.

> PRs will trigger unit and integration tests with and without race detection, linting and formatting validations, static and security checks, freshness of generated files verification. All the tests must pass before merging in main branch.

## Contributing to the code

### Required dependencies and setup

You can set everything manually if you want, it is quite simple (you can look at the CI for reference). But we also provide you with a way to
get it up and running automatically. You only need to install [Winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/). This will
be used only in the setup, you can uninstall it later.

Then, run script [`.\prepare-repository.ps1`](prepare-repository.ps1). You can simply run the script with no arguments, but if you want to see the options use `help .\prepare-repository.ps1`.

This setup is only necessary if you want to run an example or the test suite. If you merely intend to consume this module, import `github.com/ubuntu/gowsl` in your Go project and you're set.

### Building an example program

You will find an example program in [the example folder](examples/demo.go). It consists of installing an ubuntu WSL distribution,
running some asynchronous and interactive commands to it, and finally unregistering it.

To run it, complete the setup explained in the previous section and simply run:

```powershell
go run .\examples\demo.go
```

### About the test suite

The project includes a comprehensive test suite made of unit and integration tests. All the tests must pass with and without the race detector.

You can run all tests with: `go test ./...` (add `-race` for race detection).

The test suite must pass before merging the PR to our main branch. Any new feature, change or fix must be covered by corresponding tests.

## Contributor Licence Agreement

It is required to sign the [Contributor Licence Agreement](https://ubuntu.com/legal/contributors) to contribute to this project.

An automated test is executed on PRs to check if it has been accepted.

This project is covered by the [MIT License](LICENSE).

## Getting Help

Join us in the [Ubuntu Community](https://discourse.ubuntu.com/c/desktop/8) and post your question there with a descriptive tag.
