# grep(1) Examples #

* Show the lines where a pattern occurs
	* `grep pattern filename`
* ...or the ones where it doesn't
	* `grep -v pattern filename`
* ...or anywhere in all the files under a directory; "r" == recursive
	* `grep -r pattern directory`
* Search case-insensitively
	* `grep -i pattern filename`
* Show the lines where a pattern occurs, preceded by the line numbers 
	* `grep -n pattern filename`
* Only report the *count* of lines on which a pattern occurs in the
  file; only counts lines, not instances of the pattern
	* `grep -c pattern filename`
* Show matching lines, plus two lines after 
	* `grep -A 2 pattern filename`
* Show matching lines, plus two lines before
	* `grep -B 2 pattern filename`
* Show matching lines, with two lines before *and* two after
	* `grep -C 2 pattern filename`
* grep(1)'s siblings:
    * Search for a fixed string (no regexes).  Can be much faster if
      you don't really need a regex match (-i still works, tho)
        * `fgrep string filename`
    * Search for an extended regex
        * `egrep uberPattern filename`


