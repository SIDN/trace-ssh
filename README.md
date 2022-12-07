# trace-ssh

This is a small shellscript that shows you the traceroute to the ssh
server you are connected to, as well as the traceroute from the
server back to your local system.

It starts ssh in a tmux session with 3 panes:

* the main pane on the left contains the ssh session itself, 
* the pane on the top right shows an mtr trace to the destination
* the pane on the bottom right shows an mtr trace from the destination to the source

When you exit the main ssh shell, the tmux session will be terminated.

## Requirements

- ssh
- tmux, on client system
- mtr, on both client and server system

## Usage

It is recommended that you have a terminal window that is large enough to show all relevant traceroute information.

Since trace-ssh starts two ssh sessions to the server, it is also recommended that you use public key access, so that you do not need to manually authenticate twice. If you do need interactive authentication, you can switch to the remote mtr pane with the key combination ctrl+b, followed by the right arrow key, and ctrl-b followed by left to switch back to the main pane.
