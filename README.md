# hosts_editor
Custom bash script to automate the blocking/unblocking of domains from the hosts file. 

## Operations

The script have 3 basic operations:

* **Manual changes** - Open /etc/hosts on $EDITOR. Any changes to the file generate a .diff on $DIR/hosts_diff which is used to patch /etc/hosts.
* **Unblock by pattern** - Search for a pattern on /etc/hosts and comment all the lines that match it. 
* **Revert previous changes** - Revert previous changes on /etc/hosts using the .diff files. After this operation the .diff file corresponding to the pattern is removed.

