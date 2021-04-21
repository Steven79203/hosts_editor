# HOSTS EDITOR
Custom bash script to automate the blocking/unblocking of domains from the hosts file. 

## Operations

The script have 3 basic operations:

* **Manual changes** - Open /etc/hosts on $EDITOR. After any changes a .diff is generated on $DIR/hosts_diff (default = $HOME/.config/hosts_diff) which is used to patch /etc/hosts and, obviously, revert any changes.
* **Unblock by pattern** - Search for a regex pattern (EX: a Domain's URL) on /etc/hosts and comment all the lines that match it. 
* **Revert previous changes** - Revert previous changes on /etc/hosts using the .diff files. After this operation the .diff file corresponding to the pattern is removed.

