# Loop Cheat Sheet #

* while:
  <pre>
    bash$ while true; do
    > echo "hello world"
    > sleep 1
    > done
  </pre>
* for:
  <pre>
    bash$ for item in ...list...; do
    > echo $item
    > done
  </pre>

* Example from presentation:
  <pre>
    bash$ for host in $(cat list_of_hosts.txt)
    > do
    > echo "Running on $host"
    > ssh $host 'do_something --cool'
    > done
  </pre>

