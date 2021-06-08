Setup Ansible Playbooks for setting up development enviroment.

Used on:
- [WSL2](https://devblogs.microsoft.com/commandline/announcing-wsl-2/) with the [Ubuntu app](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6).

## (Required) Setting up a Linux Environment
There are a couple easy ways to get to a clean Linux environment on Windows: multipass and WSL.

### (Recommended) WSL2
Follow the [Windows Subsystem for Linux Installation Guide for Windows 10](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

## Quick Start
You'll need to get an ssh key into your new Linux environment. Afterwards, run the following:

```bash
# Clone to your home directory
git clone git@github.com:devreagi/wsl2-dev-ubuntu.git

# (Required) Set your username in playbook.yaml. While you're at it, check out the roles and vars_files too.

# Installs ansible and dependencies
sudo sh bootstrap.sh

# Run the playbook
ansible-playbook -K playbook.yaml
```

## What do you get?
This is a _somewhat_ opinionated but *lean* installation of tools that I want to have on a Linux environment. I do a lot of dev _in_ Docker containers, so often those containers will have specialized tools.

Generally, I'm running this on my primary WSL2 workspace. I also spin up a VM from time to time for specific tasks and provision it with these tools for consistency.

### Shell

> Installs basic tools like vim and sets up zsh as the default shell.

- [zsh](http://zsh.sourceforge.net/): "Zsh is a shell designed for interactive use, although it is also a powerful scripting language."
- [oh-my-zsh](https://ohmyz.sh/): "Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration."
- [vim](https://www.vim.org/): "Vim is a highly configurable text editor for efficiently creating and changing any kind of text."


### Dev tooling

> Tooling and programming languages for scripting and application development. Check prerequisite_packages.yml on var folder

## Inspiration
[jasonwc setup](https://github.com/jasonwc/setup).
