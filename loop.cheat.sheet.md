# Loop Cheat Sheet #

* while:
    bash$ while (true); do
    > echo "hello world"
    > sleep 1
    > done
* for:
    bash$ for item in ...list...; do
    > echo $item
    > done

* Example from presentation:
    bash$ for host in $(cat list_of_hosts.txt)
    > do
    > echo "Running on $host"
    > ssh $host 'do_something --cool'
    > done

