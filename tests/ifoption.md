# ifoption command

If the option is present, write value, else write default.

	$ cat << __EOF__ > sum
	> bc
	>     paste --serial --delimiter '+'
	>         ifoption --one 1 2
	>         echo
	>         echo 1
	> __EOF__

	$ rio --one-mouth ./sum --one
	< 2

	$ rio --one-mouth ./sum
	< 3
