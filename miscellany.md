# Miscellaneous Topics #

See also: man bash

* Output redirection
<pre>
# bash makes it easy to redirect stdout...
bash$ ls -1 /var/log > list_of_logfiles

# ...stderr...
bash$ grep -r foo /etc 2> /dev/null

# ...or both...
bash$ my.script >& ~/output.and.errors
# (same thing)
bash$ my.script > ~/output.and.errors 2>&1
</pre>

* Arrays
<pre>
bash$ my_list=(first second third)
bash$ echo ${my_list[1]}
second
bash$ hosts=($(cat my.host.list))
bash$ echo ${hosts[3]}
host4
bash$ echo ${hosts[${#hosts}]}
hostN
</pre>

* Conditionals
<pre>
bash$ if [[ ${my_list[1]} = "second" ]]
> then echo "yep, it is second"
> else echo "no, it is not"
> fi
yep, it is second
bash$ if [[ ${#my_list} -ge 42 ]]
> then echo "big list"
> else echo "leetle list"
> fi
leetle list
</pre>
