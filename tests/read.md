# read command

Read from stdin. It is duplicated if there are two read commands.

	$ cat << __EOF__ > list_2_then_1
	> grep '^2'
	>     read
	> grep '^1'
	>     read
	> __EOF__

	$ cat << __EOF__ | rio --one-mouth ./list_2_then_1
	> 1- First item.
	> 2- Second item.
	> 3- Third item.
	> __EOF__
	< 2- Second item.
	< 1- First item.
