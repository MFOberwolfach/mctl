= README of mctl =

== Introduction ==

mctl, the MiMa Control Script, is a python3 script for fine-tuned
start, stop and status operations on an number of remote hosts.
This includes disconnecting a host from electricity by a power
distribution unit that speaks SNMP.

mctl was written to control the interactive exhibits at the MiMa,
the Museum for Minerals and Mathematics in Oberwolfach, Germany.

== Installation ==

Make sure python3 is installed.

Copy the repository into a user's home directory and link
/home/USER/mctl/bin/mctl to /usr/bin/mctl.

== Configuration ==

Take a look at the commands help 'mctl --help' and at the
configuration files in mctl/etc/.

Configure a publickey ssh login for the user on each remote host
and endow the remote user with permissions to execute the given
shutdown command.

Further adaptions are possible and may be necessary by editing
the source code.


== Bugs and Shortcomings ==

mctl has been tested exclusively on Linux.

The command line session is assumed to be open until the command
has finished, use something like "nohup mctl shutodwn all &"
otherwise.

The command feedbacks take some time to appear. The command may
take long due to several timeouts. The status message looks ugly.

Reihenfolge bei uptime Ausgabe

== Advantages and Prospects ==

This is a configurable and extensible straightforward solution.
The hosts are handled simultaneously, while the order of the hosts
is retained.

Instead of improving this script, one should think of a good
solution for controlling remote hosts consisting of
 - a data backend
 - a service
 - a web interface
 - a command line interface


== License ==

GNU GPLv3
