# getoption command

Get command line argument.

	$ cat << __EOF__ > sum
	> bc
	>     paste --serial --delimiter '+'
	>         getoption --first
	>         echo
	>         getoption --second
	>         echo
	> __EOF__

	$ rio --one-mouth ./sum --first 2 --second 3
	< 5

	$ cat << __EOF__ > numbers
	> getoption --first
	> echo
	> getoption --second
	> echo
	> __EOF__

	$ rio --one-mouth ./numbers --first 2 --second 3
	< 2
	< 3
