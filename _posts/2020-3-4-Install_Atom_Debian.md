---
layout: post
title: Installing Atom on Debian...
---
You can install Atom on Linux using your distribution's package manager by configuring it to use one of Atom
official package repositories. This will also enable you to update Atom when new releases are published.

To install Atom on Debian, Ubuntu, or related distributions, add Atom official package repository to your system by running the following commands -

wget -qO - https://packagecloud.io/AtomEditor/atom/gpgkey | sudo apt-key add -

sudo sh -c 'echo "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main" > /etc/apt/sources.list.d/atom.list'

sudo apt-get update

You can now install Atom using apt-get (or apt on Ubuntu)

# Install Atom
sudo apt-get install atom
# Install Atom Beta
sudo apt-get install atom-beta
