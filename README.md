# mctl README

## Introduction

mctl, the MiMa Control Script, is a python3 script for fine-tuned
start, stop and status operations on an number of target hosts.
This includes disconnecting a host from electricity by a power
distribution unit that speaks SNMP.

mctl was written to control the interactive exhibits at the MiMa,
the Museum for Minerals and Mathematics in Oberwolfach, Germany.
It is meant to run on Linux.


## Installation

Make sure python3 is installed.

Copy the repository into a user's home directory and link
`/home/USER/mctl/bin/mctl` to `/usr/bin/mctl`.

In the `etc` directory copy `config.sample.ini` to `config.ini`
and `hosts.sample.ini` to `hosts.ini`.


## Configuration

Run `mctl --help` and `mctl show all` and edit the configuration
files as needed.

Configure a public key ssh login to each target host and endow the
user on the target host with permissions to execute the given
shutdown command.

Further adaptions are possible and may be necessary by editing
the source code.


## Advantages and Prospects

This is a straightforward solution, which is configurable and
extensible. The hosts are handled simultaneously, while the
output always uses their order from `hosts.ini`.

A thorough solution for controlling hosts would consist of

- a data backend
- a service
- a web interface
- a command line interface


## Bugs and Shortcomings

The command line session is assumed to be open until the command
has finished, use something like `nohup mctl shutdown all &`
otherwise.

The output does not appear until the action has finished on the
respective host.

The actions may take long due to several timeouts.

There is a twist of lines in the `status` output, which looks
ugly anyway.


## License

GNU GPLv3
