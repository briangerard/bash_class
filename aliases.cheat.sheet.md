# Aliases Cheat Sheet #

See also: The ALIASES section of 'man bash'

* An alias is a string which will be substituted for a word
  when that word appears first in a simple command
    * `alias sayfoo='echo $foo'`

* It is worth noting that aliases are only expanded once, so something
  like the following will not result in an infinite re-expansion.  
    * `alias ls='ls -AFC'`
    * And this, given the declaration above
        * `ls /foo`
    * Is exactly the same as this, without it
        * `ls -AFC /foo`

* Example from presentation
    * `alias do_cool_stuff='for host in $(cat list_of_hosts.txt); do echo "Running on $host"; ssh $host "do_something --cool"; done'`

Reminder: Use the <tt>type</tt> bash built-in command to find out what
bash would execute if you used its argument as a command.
<pre>
bash$ type do_cool_stuff
do_cool_stuff is aliased to `for host in $(cat list_of_hosts.txt); do echo "Running on $host"; ssh $host "do_something --cool"; done'
</pre>

