Bitranium Core integration/staging tree
=====================================

[![Build Status](https://travis-ci.org/bitranium-project/bitranium.svg?branch=master)](https://travis-ci.org/bitranium-project/bitranium)

https://bitranium.com

What is Bitranium?
----------------

Bitranium is an experimental digital currency that enables instant payments to
anyone, anywhere in the world. Bitranium uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. Bitranium Core is the name of open source
software which enables the use of this currency.

For more information, as well as an immediately useable, binary version of
the Bitranium Core software, see [bitranium.com](https://bitranium.com).

License
-------

Bitranium Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/licenses/MIT.

Development Process
-------------------

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/bitranium-project/bitranium/tags) are created
regularly to indicate new official, stable release versions of Bitranium Core.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md)
and useful hints for developers can be found in [doc/developer-notes.md](doc/developer-notes.md).

The developer [mailing list](https://groups.google.com/forum/#!forum/bitranium-dev)
should be used to discuss complicated or controversial changes before working
on a patch set.

Developer IRC can be found on Freenode at #bitranium-dev.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write [unit tests](src/test/README.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled in configure) with: `make check`. Further details on running
and extending unit tests can be found in [/src/test/README.md](/src/test/README.md).

There are also [regression and integration tests](/test), written
in Python, that are run automatically on the build server.
These tests can be run (if the [test dependencies](/test) are installed) with: `test/functional/test_runner.py`

The Travis CI system makes sure that every pull request is built for Windows, Linux, and macOS, and that unit/sanity tests are run automatically.

### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.

Running Node
------------
Install a node for your coin on Ubuntu Server 18.04 with the following tutorial.

Update your Ubuntu server with the following command:

sudo apt-get update && sudo apt-get upgrade -y

Install the required dependencies with the following command:

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev libminiupnpc-dev libzmq3-dev libprotobuf-dev protobuf-compiler unzip software-properties-common cmake -y

Install the repository ppa:bitcoin/bitcoin with the following command:

sudo add-apt-repository ppa:bitcoin/bitcoin

Confirm the installation of the repository by pressing on the enter key. enter

Install Berkeley DB with the following command:

sudo apt-get update && sudo apt-get install libdb4.8-dev libdb4.8++-dev -y

Download the Linux daemon for your wallet with the following command:

Download : https://bitranium.com/download/bitracoin-deamon-linux.tar.gz

Extract the tar file with the following command:

tar -xzvf bitracoin-daemon-linux.tar.gz

Download the Linux tools for your wallet with the following command:

Download: https://bitranium.com/download/bitracoin-qt-linux.tar.gz

Extract the tar file with the following command:

tar -xzvf bitracoin-qt-linux.tar.gz

Type the following command to install the daemon and tools for your wallet:

sudo mv bitracoind bitracoin-cli bitracoin-tx /usr/bin/

Create the data directory for your coin with the following command:

mkdir $HOME/.bitracoin

Open nano.

nano $HOME/.bitracoin/bitracoin.conf -t

Paste the following into nano.

rpcuser=rpc_bitracoin
rpcpassword=dR2oBQ3K1zYMZQtJFZeAerhWxaJ5Lqeq9J3
rpcallowip=127.0.0.1
listen=1
server=1
txindex=1
daemon=1
addnode=45.141.151.10
addnode=45.141.151.11
addnode=45.141.151.12
addnode=45.141.151.13
addnode=45.141.151.14
addnode=45.141.151.15
addnode=45.141.151.19

Save the file with the keyboard shortcut ctrl + x.

Type the following command to start your node:

bitracoind
