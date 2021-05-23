# fish-shop/install-plugin-manager

[![License](https://img.shields.io/badge/license-MIT-blue)](http://opensource.org/licenses/mit-license.php) [![fish](https://img.shields.io/badge/fish-3.2.2-blue)](https://fishshell.com) [![Issues](https://img.shields.io/github/issues/fish-shop/install-plugin-manager)](https://github.com/fish-shop/install-plugin-manager/issues)

A GitHub action for installing a [fish shell](https://fishshell.com) plugin manager.

## Prerequisites

This action requires the [fish shell](https://fishshell.com). You can install it within jobs in your workflow using the [install-fish](https://github.com/fish-actions/install-fish) action.

## Usage

Add a suitable `uses` step to your GitHub [workflow](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions) and specify the plugin manager to be installed by providing a value for the `plugin-manager` input as shown below:

```yaml
jobs:
  install-plugin-manager:
    runs-on: ubuntu-latest
    steps:
      - name: Install fish shell plugin manager
        uses: fish-shop/install-plugin-manager@1.0.0
        with:
          plugin-manager: fisher
```

## Supported plugin managers

The following table lists the supported plugin managers and the corresponding `plugin-manager` input name to use in your workflow:

| Plugin manager                                         | Action input name |
|--------------------------------------------------------|-------------------|
| [Fisher](https://github.com/jorgebucaran/fisher)       | `fisher`          |
| [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish) | `oh-my-fish`      |
| [plug.fish](https://github.com/kidonng/plug.fish)      | `plug.fish`       |

## Managing plugins

After installing one of the supported plugin managers listed above you may interact directly with it during subsequent steps of your workflow. This means you can install, remove, and manage plugins as desired to satisfy your particular use case.

For example, to install the [Pond](http://github.com/marcransome/pond) plugin using the [Fisher](https://github.com/jorgebucaran/fisher) plugin manager:

```yaml
...
steps:
  ...
  - name: Install Pond plugin with Fisher
    run: fisher install marcransome/pond
```

## License
`fish-shop/install-plugin-manager` is provided under the terms of the [MIT License](http://opensource.org/licenses/mit-license.php).

## Contact
Email me at [marc.ransome@fidgetbox.co.uk](mailto:marc.ransome@fidgetbox.co.uk) or tweet [@marcransome](http://www.twitter.com/marcransome).
