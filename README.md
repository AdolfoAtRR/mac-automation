# MacOS Setup with Ansible

This repository contains an Ansible configuration for setting up a Mac from scratch. It's primary purpose is setting up a new Mac from scratch, but I endeavor to also use it for adding new software as I go so that it remains up to date. At the moment it's being used for setting up M1 based Macs running MacOS Monterey.

## Getting Started

There's a simple shell script in `bin/bootstrap` which will perform the initial steps of:

1. Installing Xcode
2. Installing Ansible
3. Fetching required Ansible roles and collections

And then runs the main playbook `ansible_osx.yml`.

For future updates, `bin/apply` can be used to run just the Ansible playbook without the setup commands.

It's important to note that this isn't designed to be particularly robust, particularly when it comes to required env vars, it may be required to run this. Then close the terminal and open it again and re-run and then repeat this process a few times.

use `ansible-playbook -i inventory ansible_osx.yml -vvv -K` for asking for sudo permissions, for inventory file can be
something like
```
[localhost\]
your-host.local
```
