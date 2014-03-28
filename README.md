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

## Suggested workflow

This tool is intended for people who need to connect to a number of different servers from a number of different workstations and want to have a different key pair on each (a good idea from a security perspective as you can selectively revoke keys if you e.g. lose your laptop). 

I suggest that after you've cloned the repo and added your own pubkeys and servers, you commit to a new branch and push that to your own (probably private) git repo. This way you have the public key from each of your workstations and your server list easily accessible and modifiable. When you need to add/remove a key/server, do so, run `./key-sync` and push the changes back to your repo.

