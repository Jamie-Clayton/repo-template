# Versioning

The software versioning strategy is configured in the GitVersion.yml file which is configured with Conventional Commits to provide Semantic Versioning 2.0 results

## Semantic Versioning

Given a version number **MAJOR.MINOR.PATCH**, increment the:

**MAJOR** version when you make incompatible API changes

**MINOR** version when you add functionality in a backwards compatible manner

**PATCH** version when you make backwards compatible bug fixes

## Git Version

GitVersion is a tool that generates a Semantic Version number based on your Git history. The version number generated from GitVersion can then be used for various different purposes, such as:

Stamping a version number on artifacts (packages) produced during build.
Exposing the version number to the build server to version the build itself.
Patching AssemblyInfo.cs (and similar) files with the version number during the build, so the version number is embedded within the compiled binaries themselves.

```bash
gitversion init
```

## Conventional Commits

The Conventional Commits specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of. This convention dovetails with SemVer, by describing the features, fixes, and breaking changes made in commit messages.

```bash
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

The commit contains the following structural elements, to communicate intent to the consumers of your library:

1. **fix:** a commit of the type fix patches a bug in your codebase (this correlates with PATCH in Semantic Versioning).

2. **feat:** a commit of the type feat introduces a new feature to the codebase (this correlates with MINOR in Semantic Versioning).

3. **BREAKING CHANGE:** a commit that has a footer BREAKING CHANGE:, or appends a ! after the type/scope, introduces a breaking API change (correlating with MAJOR in Semantic Versioning). A BREAKING CHANGE can be part of commits of any type.
types other than fix: and feat: are allowed, for example @commitlint/config-conventional (based on the the Angular convention) recommends build:, 

4. **chore:**, ci:, docs:, style:, refactor:, perf:, test:, and others.

5. footers other than BREAKING CHANGE: <description> may be provided and follow a convention similar to [git trailer](https://git-scm.com/docs/git-interpret-trailers) format.

## References

- [Semantic Versioning](https://semver.org/)
- [Git Version](https://gitversion.net/docs/reference/configuration)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)