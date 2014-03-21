# key-sync

A simple bash script to replace the `authorized_keys` file on each of your servers with a provided list of public keys.

## Setup

1. Clone the repo
2. Edit the `servers` file and add each of your servers to the `SERVERS` array in `user@host` format
3. Copy each of your public keys (typically located at `~/.ssh/id_rsa.pub`) to the `pubkeys` directory.
4. Run `./key-sync`

## Warning

This script **replaces** the existing `authorized_keys` on each server.

If you need a specific public key to access any of your servers, make sure you've copied that key to your `pubkeys` directory before running `key-sync` or else you'll lock yourself out of your server!





