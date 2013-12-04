# find(1) Examples #

* All items with "something" in their names
    * `find /somewhere -name '*something*'`
* All files larger than 2 MiB in size
    * `find /somewhere -size +2M`
* Or both...
    * `find /somewhere -size +2M -a -name '*something*'`
* Things modified within the past day...
	* `find /somewhere -mtime -1`
* ...or those modified *more* than a day ago
	* `find /somewhere -mtime +0`
* Stuff modified more recently than "foo"
	* `find /somewhere -newer /path/to/foo`
* Run something on each entry it finds
	* `find /somewhere -name '*something*' -exec chmod 644 '{}' \;`
* And of course...
    * `find /your_base -name '*' -exec chgrp us '{}' \;`


