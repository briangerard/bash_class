# xargs(1) Examples #

xargs(1) takes stdin and constructs a command from it.

* Run grep(1) on a list of files
    * `cat file_list | xargs grep -H pattern`
    * Basically the same as running
        * `grep pattern file1 file2 file3 ...`
    * And more efficient than using find(1)
        * `find . -name 'file*' -exec grep -H pattern '{}' \;`
* The -n option tells xargs to only use a certain number of items
  from stdin for each constructed command
    * `cat host_list | xargs -n 1 host`
    * Looks up each host in DNS, one at a time.  Without the '-n 1', host(1)
      would take the first host as the name to look up, the second as the DNS
      server to use, and would simply be very confused about the fact that it
      was given anything more than that.
* The -I option allows xargs to insert the values it pulls from stdin somewhere
  other than at the end of the command.
    * `cat files_to_copy | xargs -I THEM /bin/cp THEM /somewhere`
    * Useful with find(1), for example...
        * `find /active -mtime +30 | xargs -I THEM /bin/mv THEM /archive`
* *If* you use the find+xargs construct, you need two more options for safety
    * find's -print0 (that's print<zero>)
    * xargs's -0 (that's -<zero>), a.k.a. --null
    * find /my/logs -mtime +30 -a -type f -print0 | xargs -0 /bin/rm
        * Ensures that find(1) separates its results with NULLs, and that
          xargs(1) looks for a NULL to delimit its incoming arguments.

