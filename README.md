![Dash](https://raw.githubusercontent.com/IFTTT/dash/images/images/dash.png "Dash")

# Dash

## What is this for?

`Dash` is a OSX setup tool forked from IFTTT/dash.
Install homebrew and ansible. and run ansible-playbook.

## TL;DR

    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/senyoltw/dash/master/bin/bootstrap)"

## Recommend
Clone "your" dotfiles repository before running the bootstrap script.  
If you made `osx/playbook.yml` and `osx/Brewfile` file, playbook load it and run.

    git clone https://github.com/senyoltw/dotfiles ~/dotfiles #example

## Step-By-Step Setup

### Run the bootstrap script

This script will install the following:

- Homebrew with XCode Command Line Tools
- Ansible
- git clone this repository `~/.dash`

And run ansible-playbook [`~/.dash/ansible/mac.yml`](https://github.com/senyoltw/dash/blob/master/ansible/mac.yml)

- ~/.dash/ansible/mac.yml
  - Update Homebrew, ansible
  - Install or Update homebrew/cask, homebrew/bundle, mas-cli/mas
  - (Optional)run ansible-playbook.
    - ~/dotfiles/osx/playbook.yml (if exists)
  - (Optional)make install dotfiles
    - ~/dotfiles/Makefile (if exists and ~/dotfiles/osx/playbook.yml not exists)
  - (Optional)Install OSX apps by [homebrew-bundle](https://github.com/Homebrew/homebrew-bundle)
    - ~/dotfiles/osx/Brewfile (if exists)

It should run idempotently, meaning you should be able to run it as many times as you want and it won't hurt anything. If it fails due to a temporary condition (like network issues), running it again should pick up where it left off. If new items are added to the script, running it against a functioning environment should only add the new things.

    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/senyoltw/dash/master/bin/bootstrap)"

If you want to update the packages you have installed, you can use

    ~/.dash/bin/update 

## What is dotfiles?
See. https://dotfiles.github.io/  
Sample. https://github.com/senyoltw/dotfiles

## What is Brewfile?
See. https://docs.brew.sh/Manpage#bundle-subcommand  
- Hou to make Brewfile  
`brew bundle dump: Write all installed casks/formulae/images/taps into a Brewfile.`

## License

`Dash` is available under the MIT license. See the LICENSE file for more info.
