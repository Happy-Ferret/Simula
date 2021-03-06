Building with Nix
=================

The easiest way to build Simula is to install `nix` and run::

    NIXPKGS_ALLOW_UNFREE=1 stack --nix build
    source ./swrast.sh # only needs to be run once

Nix automatically downloads every non-Haskell dependency for this project and places them in */nix/store* in such a way that they don't conflict with your current distro's libraries. Running *stack* with these flags tells it how to find these libraries. The *swrast.sh* script tells nix how to find your system's OpenGL drivers.

If you don't already have *nix* installed, you can get it from your distro's package manager, or run

``curl https://nixos.org/nix/install | sh``

To use *simulavr* see :ref:`simulavr-usage`.

Note on NixOS:
Currently the project needs SteamVR in order to run, which currently doesn't work on NixOS. You will as such be unable to test the end result. One of the goals of the project is to remove this dependency and enable running Simula using non-VR hardware.
