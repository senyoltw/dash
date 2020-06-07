![Dash](https://raw.githubusercontent.com/IFTTT/dash/images/images/dash.png "Dash")

# Dash

## What is this for?

`Dash` is a OSX setup tool forked from IFTTT/dash.
Install homebrew and ansible. and do ansible-playbook.

## The tl;dr Version

    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/senyoltw/dash/master/bin/bootstrap)"

## Step-By-Step Setup

### Terminology

**Host** or **host machine** refers to your physical computer.

### Run the bootstrap script

This script will install the following:

- Homebrew with XCode Command Line Tools
- Ansible

and do ansible-playbook.

- ansible/mac.yml

It should run idempotently, meaning you should be able to run it as many times as you want and it won't hurt anything. If it fails due to a temporary condition (like network issues), running it again should pick up where it left off. If new items are added to the script, running it against a functioning environment should only add the new things.

## License

`Dash` is available under the MIT license. See the LICENSE file for more info.
