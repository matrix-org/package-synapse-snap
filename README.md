# Synapse snap package

Snaps are universal Linux packages.

## Build

To build this snap, Ubuntu 16.04 or newer is required.

    $ sudo apt install git snapcraft
    $ git clone https://github.com/matrix-org/package-synapse-snap
    $ cd package-synapse-snap
    $ snapcraft

## Install

The built snap can be installed in any of the Linux distributions that support
snaps. In Ubuntu 16.04 or newer, snapd comes preinstalled. In the others,
install if following the steps in: http://snapcraft.io/docs/core/install

Then, install the snap:

    $ sudo snap install *.snap --dangerous

The dangerous flag is required because the snap you just built is not signed by
the upstream developers.

## Test

Set up a homeserver:

    $ synapse.homeserver --generate-config --server-name machine1.local --config-path homeserver.yaml --report-stats=yes

Start the server:

    $ synapse.synctl start

Register a user:

    $ synapse.register-new-matrix-user -c homeserver.yaml https://localhost:8448

Open the demo web client at https://localhost:8448 using a web browser.
