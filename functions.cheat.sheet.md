# Functions Cheat Sheet #

See also: The FUNCTIONS section of 'man bash'

Reminder: Aliases are expanded *before* functions, so if you have both
'alias foo' and 'function foo', and you run 'foo', you'll get the alias.
Use the 'unalias' bash built-in to undefine an alias.

<pre>
bash$ function do_cool_stuff () {
> for host in $(cat list_of_hosts.txt); do
> echo "Functioning on $host"
> ssh $host "do_something --cool"
> done
> }
</pre>

<pre>
bash$ function here_n_there () {
> echo "This goes to stdout"
> ls /no/such/file
> } > ~/herethere.out 2> ~/herethere.err
bash$ here_n_there
bash$ cat ~/herethere.out
This goes to stdout
bash$ cat ~/herethere.err
ls: cannot access /no/such/file: No such file or directory
</pre>

<pre>
# bash will protect you from some mistakes, such as a missing semicolon
bash$ function bad_syntax_yo () {
> echo "This is okay"
> for i in 1 2 3 4; do
> echo "Not ok - no semicolon here ->" done
> }
bash: syntax error near unexpected token `}'
bash$ type bad_syntax_yo
bash: type: bad_syntax_yo: not found
</pre>


<pre>
# Missing command?  Runtime error.
bash$ function good_syntax_bad_command () {
> echo "This is okay"
> this is not a command
> }
bash$ good_syntax_bad_command
This is okay
-bash: this: command not found
bash$
</pre>

<pre>
# We can modify the function to pick a host
bash$ function do_cool_stuff () {
> if [[ $# -gt 0 ]]
> then the_hosts=($@)
> else the_hosts=($(cat list_of_hosts.txt))
> fi
> for host in ${the_hosts[*]}; do
> echo "Functioning on $host"
> ssh $host "do_something --cool"
> done
> }
</pre>


