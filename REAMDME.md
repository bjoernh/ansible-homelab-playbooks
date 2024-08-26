# Ansible Playbooks for Homelab Setup

This repository contains a collection of Ansible playbooks designed to set up essential tools and configurations on my homelab environment. These playbooks automate the installation and configuration of Docker, ZSH, Rust packages, and Neovim for both x86-64 and ARM64 architectures.

## Playbook Overview

### 1. docker.yaml

This playbook handles the installation and configuration of Docker on the `homelab` host.

- Configures Docker daemon options for log management.
- Adds the specified user (ansible user) to Docker users.
- Checks the installed Docker version.
- Executes the `geerlingguy.docker` role for Docker installation and configuration.

### 2. zsh-rust-tools.yaml

This playbook installs various tools and utilities on the `homelab` host using `cargo` as the package manager.

- Installs basic development tools: Git, ZSH, g++, and ripgrep.
- Links the cargo binary to `/usr/local/bin`.
- Installs multiple utilities via `cargo binstall`, including bottom, difftastic, eza, sd, xh, xcp, procs, bat, navi, and dust.
- Executes the `hurricanehrndz.rustup` role for Rust setup.

### 3. neovim-x86.yaml

This playbook installs Neovim on an `x86-64` architecture system.

- Installs prerequisite packages: Git and unzip.
- Downloads and extracts Neovim.
- Links the Neovim binary to `/usr/local/bin`.
- Clones NvChad configuration for Neovim setup.
- Prints a manual step for further Neovim setup.

### 4. neovim-arm64.yaml

This playbook installs Neovim on an `ARM64` architecture system.

- Installs prerequisite packages: Git, unzip, build-essential, gettext, and cmake.
- Creates a temporary directory for the build.
- Clones the Neovim repository and builds the project.
- Installs Neovim to `/usr/local/bin`.
- Clones NvChad configuration for Neovim setup.
- Prints a manual step for further Neovim setup.

### 5. .ansible.cfg

This configuration file sets up the default inventory location and roles path for Ansible.
