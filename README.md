# HOSTS EDITOR
Custom bash script to automate the blocking/unblocking of domains from my hosts file. Basically any edit on the file that can be tracked with diff/patch.

## Operations
Environment variables defined:
* EDITOR - Default editor used on manual mode (default: vim)
* HOSTS_TMP - Temporary copy from $HOSTS that receives the modifications on manual mode (default: /tmp/hosts.tmp)
* HOSTS - Original file (default: /etc/hosts)
* PATT_TMP - File with the modifications from the pattern mode (default: /tmp/pattern.tmp)
* DIFF_DIR - Directory with the diffs (default: $HOME/.config/hosts_diff)

The script have 3 operations:

* **Manual changes** - Opens $HOSTS on $EDITOR. After any changes a .diff is generated on $DIFF_DIR which is used to patch $HOSTS. The diff files by default tag the files with date-time but you can insert a custom tag.
* **Unblock by pattern** - Search a pattern by regex (EX: a domain's URL) on $HOSTS and comment all the lines that match it. Lines already commented are ignored by the script to avoid redundance. 
* **Revert previous changes** - Revert the patches from a .diff file and delet it.

## DEPENDENCIES
* bat - alternative to cat made in rust

## NOTES
Yes, I know you can use Git for this, but I wanted to make my own implementation and also to learn/practice some shell scripting. 

## KNOWN BUGS
None at the moment
