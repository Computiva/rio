# One mouth river

All the data flows to the standard output.

	$ cat << __EOF__ > echo_pair_numbers
	> grep '[246]'
	>     echo 2
	>     echo 3
	>     echo 4
	> __EOF__

	$ rio --one-mouth echo_pair_numbers
	< 2
	< 4

	$ cat << __EOF__ > sum
	> bc
	>     paste --serial --delimiter '+'
	>         echo 3
	>         echo 4
	> __EOF__

	$ rio --one-mouth sum
	< 7

	$ cat << __EOF__ > sum2
	> bc
	>     paste --serial --delimiter '+'
	>         echo 3
	>         echo 4
	>     paste --serial --delimiter '*'
	>         echo 2
	>         echo 3
	> __EOF__

	$ rio --one-mouth sum2
	< 7
	< 6
