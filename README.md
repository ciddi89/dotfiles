<h1 align="center">dotfiles</h1>

<p align='center'>Here you will find my personal dotfiles.</p>

## ⚠️ Requirements

#### Commands

- sudo (maybe)
- git
- [GNU stow](https://github.com/aspiers/stow)

## 🚀 Installation

Clone this repository:

    git clone https://github.com/ciddi89/dotfiles.git ~/dotfiles

### Using [GNU Stow](https://www.gnu.org/software/stow/) _(recommended)_

Install GNU Stow _(if not already installed)_

    Mac:      brew install stow
    Debian:   apt install stow
    Ubuntu:   apt-get install stow
    Fedora:   yum install stow
    Arch:     pacman -S stow

Then simply use stow to install the dotfiles you want to use:

    cd ~/dotfiles
    stow zshrc

Or to install all my dotfiles config:

    cd ~/dotfiles && \
      stow zshrc && \
      stow starship \

We may get some warning messages like the following one:

    cd ~/dotfiles
    stow git
    WARNING! stowing git would cause conflicts:
      * existing target is neither a link nor a directory: .gitconfig
    All operations aborted.

Or

    WARNING! stowing git would cause conflicts:
      * existing target is not owned by stow: .gitconfig
    All operations aborted.

This means that the file `.gitconfig` (or any other file name that appear in the warning) exists before the symlinking. We need to
manually change its name so GNU Stow can create the symlink. My recommendation is
to rename it:

    mv ~/.gitconfig ~/.gitconfig.old
