---
title: How to install node.js on Mac OSX
author: George Ornbo
layout: post
tags:
- installation
- osx
---
![node.js logo][10]

On OSX you have three ways you can install node.js

* [from homebrew (a pacakge manager for OSX)][11]
* [from a single click installer][12]
* [from source][13]

I recommend you install from homebrew.

<h2 id="homebrew">Installing from hombrew (recommended)</h2>

Homebrew is a package manager for OSX that makes installing software trivial. I strongly recommend that you use hombrew to install node.js and other software on OSX.

To be able to use hombrew you will need to install [Xcode][2]. Xcode is available for free through the app store. It is a hefty download and it will take a while to install so be prepared for this to take around 30 minutes depending on the speed of your internet connection.

![Xcode][3]

Follow the [homebrew installation instructions][9] and once you have installed hombrew you can install node.js with:

    brew install node

Once you have successfully installed node hombrew will issue some further instructions

    Please add /usr/local/lib/node_modules to your NODE_PATH environment variable to have node libraries picked up.  

You can do this using 

    echo 'export NODE_PATH=/usr/local/lib/node_modules' >> ~/.profile
    source ~/.profile

When new versions are released you can upgrade with:

    brew update && brew upgrade

<h2 id="single-click">Installing from a single click installer</h2>

There is a single click installer available for node.js, maintained by Philipp Dunkel. This also installs [npm][8], node's package manager.

First download the latest version to your Mac from the [project site][5]

![Single click installation of node.js][7]

Then install node.js by double clicking the .pkg file. The installer will guide you through the process of installing node.js

![node.js installation via .pkg file][6]

<h2 id="source">Installing from source</h2>

You may wish to download and compile the source code. You will find the latest source available on the [node.js][4] site.

    mkdir ~/src
    cd ~/src
    curl -O http://nodejs.org/dist/node-v0.4.11.tar.gz
    tar -xzf node-v0.4.11.tar.gz
    cd node-v0.4.11
    ./configure
    make
    sudo make install

## Checking everything is ok

If everything is ok you should be able to type node at the command line and enter an interactive prompt.

    node
    >

## Troubleshooting

You may find that node is not in your path after installation

    which node
    node not found

This means that although you have installed node it is not in your PATH. PATH tell your shell (bash, zsh or whatever) where to look for programs. 

You can see the contents of the PATH variable by typing the following at the command prompt

    echo $PATH

If you don't see the path to where you installed node you will need to add it.

If you installed node to $HOME/local/node

    echo 'export PATH=$HOME/local/node/bin:$PATH' >> ~/.profile
    echo 'export NODE_PATH=$HOME/local/node:$HOME/local/node/lib/node_modules' >> ~/.profile
    source ~/.profile

You should then find that node is in your PATH and works. 

## Problems?

If you are still experiencing problems use the comments below. 

[1]: http://mxcl.github.com/homebrew/
[2]: http://itunes.apple.com/us/app/xcode/id448457090
[3]: http://cdn.nodejsbook.io/images/articles/xcode.png
[4]: http://nodejs.org/#download
[5]: https://sites.google.com/site/nodejsmacosx/
[6]: http://cdn.nodejsbook.io/images/articles/nodejs-installation-via-pkg.png
[7]: http://cdn.nodejsbook.io/images/articles/single-click-installation-of-nodejs.png
[8]: http://npmjs.org/
[9]: https://github.com/mxcl/homebrew/wiki/installation
[10]: http://nodejs.org/logos/nodejs-dark.png
[11]: #homebrew
[12]: #single-click
[13]: #source
