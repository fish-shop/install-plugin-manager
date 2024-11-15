<img alt="fish" src="images/fish-market.png" width="160" align="right">

# fish-shop/install-plugin-manager

[![OpenSSF Scorecard](https://img.shields.io/ossf-scorecard/github.com/fish-shop/install-plugin-manager?label=OpenSSF%20Scorecard)](https://securityscorecards.dev/viewer/?uri=github.com/fish-shop/install-plugin-manager) [![Tests](https://img.shields.io/github/actions/workflow/status/fish-shop/install-plugin-manager/test.yml?branch=main&color=brightgreen&label=tests)](https://github.com/fish-shop/install-plugin-manager/actions) [![Issues](https://img.shields.io/github/issues/fish-shop/install-plugin-manager)](https://github.com/fish-shop/install-plugin-manager/issues) [![Dependabot](https://img.shields.io/badge/dependabot-active-brightgreen.svg)](https://github.com/fish-shop/install-plugin-manager/network/dependencies) [![License](https://img.shields.io/badge/license-MIT-blue)](https://opensource.org/licenses/mit-license.php) [![fish](https://img.shields.io/badge/fish-3.2.2-blue)](https://fishshell.com)

A GitHub action for installing a [fish shell](https://fishshell.com) plugin manager.

<hr>

## Prerequisites

This action requires [fish shell](https://fishshell.com). You can install it using the [fish-shop/install-fish-shell](https://github.com/fish-shop/install-fish-shell) action.

## Usage

Add a suitable `uses` step to your GitHub [workflow](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions) and specify the plugin manager to be installed by providing a value for the `plugin-manager` input as shown below:

```yaml
- name: Install Fisher plugin manager
  uses: fish-shop/install-plugin-manager@v2
  with:
    plugin-manager: fisher
```

## Supported plugin managers

The following table lists the supported plugin managers and the corresponding `plugin-manager` input value to use in your workflow:

| Plugin manager                                         | `plugin-manager` value |
|--------------------------------------------------------|------------------------|
| [Fisher](https://github.com/jorgebucaran/fisher)       | `fisher`               |
| [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish) | `oh-my-fish`[^1]       |
| ~~[plug.fish](https://github.com/kidonng/plug.fish)~~  | ~~`plug.fish`~~[^2]    |

[^1]: [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish) is currently [unmaintained](https://github.com/oh-my-fish/oh-my-fish/issues/947) and support for this plugin manager may be removed in a future update.
[^2]: [plug.fish](https://github.com/kidonng/plug.fish) support was removed in `v2.0.0` due to upstream changes that are generally incompatible with the use of this plugin manager in the context of GitHub Actions.

## Managing plugins

After installing one of the supported plugin managers listed above, you may interact with it directly in subsequent steps of your workflow to install, remove, and manage plugins as desired.

For example, to install the [Pond](http://github.com/marcransome/pond) plugin using [Fisher](https://github.com/jorgebucaran/fisher):

```yaml
- name: Install Pond plugin with Fisher
  run: fisher install marcransome/pond
  shell: fish {0}
```

Refer to the official documentation for the specific plugin manager being used for additional information.

## Action versions

Use one of the following patterns when specifying the version reference for this action in your workflow (i.e. the `{ref}` value in `uses: fish-shop/install-plugin-manager@{ref}`):

| Pattern  | Example   | Description                                                            |
|----------|-----------|------------------------------------------------------------------------|
| `vX`     | `v2`      | the latest `v2.*` release including non-breaking changes and bug fixes |
| `vX.Y`   | `v2.1`    | the latest `v2.1.*` release including bug fixes                        |
| `vX.Y.Z` | `v2.1.0`  | the `v2.1.0` release only                                              |

> [!TIP]
> The recommended pattern is `vX` (e.g. `v2`). This will ensure that the version of the action used in your workflow includes the latest non-breaking changes and bug fixes, and guarantees compatibility with previous versions of that major release number.

Using a `main` branch reference in your workflow is _not_ recommended as this branch may include breaking changes intended for the next major release.

## Other GitHub actions

A number of related composite actions are also available from the [fish-shop](https://github.com/fish-shop) 🐟. Check them out:

* [fish-shop/indent-check](https://github.com/fish-shop/indent-check) - A GitHub action for checking indentation in fish shell files
* [fish-shop/install-fish-shell](https://github.com/fish-shop/install-fish-shell) - A GitHub action for installing fish shell
* [fish-shop/syntax-check](https://github.com/fish-shop/syntax-check) - A GitHub action for syntax checking fish shell files
* [fish-shop/install-plugin](https://github.com/fish-shop/install-plugin) - A GitHub action for installing fish shell plugins
* [fish-shop/run-fishtape-tests](https://github.com/fish-shop/run-fishtape-tests) - A GitHub action for running Fishtape tests

## Acknowledgements

* Fish market icon made by [Freepik](https://www.flaticon.com/authors/freepik) from [www.flaticon.com](https://www.flaticon.com/)

## License
`fish-shop/install-plugin-manager` is provided under the terms of the [MIT License](https://opensource.org/licenses/mit-license.php).

## Contact
Email me at [marc.ransome@fidgetbox.co.uk](mailto:marc.ransome@fidgetbox.co.uk) or [create an issue](https://github.com/fish-shop/install-plugin-manager/issues).
