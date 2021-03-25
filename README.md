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
You would need atkeast 4gb memory with 60gb ssd and 2vCPU VPS

On your Ubuntu cli type
<code>
sudo apt-get update 
</code>
<code>
sudo apt-get install build-essential
 </code>
 <code>
sudo apt-get install autoconf libtool pkg-config libboost-all-dev libssl-dev libprotobuf-dev protobuf-compiler libevent-dev libqt4-dev libcanberra-gtk-module libdb++-dev  
</code>

Then 
cd /opt/

wget https://github.com/bitranium/bitranium/releases/download/1.0.0/linux-binaries.zip
unzip linux-binaries
mv linux-binaries bitranium
cd bitranium
./bitraniumd

This will create a new directory in /root/.bitranium/

You can stop bitraniumd and create a new bitranium.conf in /root/.bitranium/

Something like this

rpcuser=rpcUsername
rpcpassword=passwordhere
rpcport=3118
rpcallowip=127.0.0.1
daemon=1
addresstype=legacy

Your Bitranium will be running and RPC will be open on port 3118
# bitranium
