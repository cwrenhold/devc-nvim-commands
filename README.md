# Introduction

This is a simple script to allow you to use the [devcontainercli](https://github.com/devcontainers/cli) to install neovim and copy your existing configuration into the devcontainer. This allows you to have a configuration within the container which is separate from your local machine, for example to have LSPs and other tools installed within the container which you don't want to install on your local machine.

# Dependencies

To use this script, you will need to have the following:

- [neovim](https://neovim.io/) (obviously)
- [Docker](https://www.docker.com/)
- [devcontainercli](https://github.com/devcontainers/cli)

# Setup

To use this script, you will need to have the `devc-nvim` script in your path. You can do this by adding the directory containing the script to your path, or by copying the script to a directory which is already in your path. For example, you could clone this repository and then add that directory to your path, and then either copy the `devc-nvim` script to `/usr/local/bin` or create a symlink to it from there.

As this is an executable script, you may need to make it executable with `chmod +x devc-nvim` if it isn't already.

# Usage

To use this, you need to be in a directory which contains a devcontainer configuration. There are a few ways to use this script in such a location:

- `devc-nvim nvim` - This will start up neovim in the container from the workspace root
- `devc-nvim clean` - This will remove any existing neovim configuration in the container
- `devc-nvim install` - This will install neovim in the container
- `devc-nvim install-nightly` - This will install the nightly version of neovim in the container
- `devc-nvim install-dependencies` or `devc-nvim install-deps` - This will install the dependencies for neovim in the container
- `devc-nvim help` - This will display the help message, including the available commands

If no command is provided, the script will default to starting neovim in the container.

# Caveats

This script is very simple and does not handle any complex cases. Due to this, it assumes that your configuration is in the standard location (`~/.config/nvim`) and that we don't need to worry about sharing state or anything like that.

