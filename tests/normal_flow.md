# Normal flow

	$ cat << __EOF__ > echo_3
	> seq 5
	> grep 3
	> __EOF__

	$ rio echo_3
	< 3
