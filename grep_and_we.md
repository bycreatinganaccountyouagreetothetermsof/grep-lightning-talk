# grep and we

###### by lain (we/us)

---

# grep is a cli tool for searching
the name is an acronym,

* ##### G`search for a`
* ##### R`egular`
* ##### E`xpression and`
* ##### P`rint results`

---

#### usually files, but
### works on anything you can shove into a pipe

---

#### grep is older than you

unless you are like 48 years old. the specific date is coolly debated and forever unknowable but Kenneth Tomlinson, the original guy who thought search started with G, has confirmed hisself that grep was created sometime before March 3, 1973

![[ken_email.png|400]]

https://medium.com/@rualthanzauva/grep-was-a-private-command-of-mine-for-quite-a-while-before-i-made-it-public-ken-thompson-a40e24a5ef48

--- 

# theres a man

the worst way to get to know grep is to read the manpage by typing `man grep`

![[mansplaining_page.gif|500]]

---

# oursplaining

of course the manpage is very long and boring and this is a lightning talk so

![[tldr_page.png|500]]

---

# ok what

---

##### scene: ur typin and u cant find yr stuff
### grep to the rescue

![[grep_rescue.png|500]]

---

#### grep options i think are important

##### `-i`
`--ignore-case` makes your search case-insensitive. i type it by reflex and if it interferes i can just search again without `-i`

##### `-R` or `-r`
`--recursive` lets you search inside folders. normally when grep sees a dir its like "uhhh nope too much work" and skips over but you can tell that b to look in and leave no file unturnt. you probs wanna use this if you have a project of any complexity

##### `-v`
`--invert-match` is hella cool because it lets you say show everything EXCEPT. sick if ur grepping with pipes!!

##### `-I`
`--binary-file=without-match` to ignore binary files. often doesnt matter but maybe dont wanna grep binary files. takes FOREVER and u only get yes/no and can't edit them anyway so who cares

---

## whats pipes
 pipes is not grep but you should use it with grep often. many commands in the terminal can be chained with the otherwise-useless pipe character `|`

![[gay_cow.png|400]]

so if you get a big set of results from your first grep, you can refine it with a second grep.

---

# pipe example

---

say you lookin for a thing.  well you found it! but theres too many thing...

![[big_greppy.mp4]]
 
 ---
 
 # pipe it
 
 ---
 
 ![[lil_greppy.mp4]]
 
 ---
 
 ### regular expressions
 
 a huge part of gREp is the use of regular expressions, an arcane language worse than list comprehensions for writing cryptic little programs that match text in hideously complex ways.
 
 nobody knows the true depths of this ancient power. anyone who reads too much about regexps will lose touch with reality and inevitably write a lot of bad code and get fired before they can explain to the rest of their team what horrible secrets they've learned.
 
 regexp have only one rule: never process html, lest you summon the demon s-ta c'kö vɘr*ﬂ*œ'w
 
 ---
 
 ## regexp and grep
 
in the normal mode, grep uses a reduced set of regular expressions, but there's an extended mode called `egrep` or activated with the `-e` flag that does more stuff. you should probably stick to the restricted mode to preserve your sanity.

---

##### `grep "some.thing" afile.py`
the period `.` character in grep means "any character" and could match the text "some" and "thing" with any character between them. for example "someathing", "some2thing", "some!thing", "some thing", and so on.
##### `grep "^firstthing" somefile.py`
the caret `^` character in regexp means "beginning of the line" and will help you match things at the beginning of a line only
#####  `grep "lastthing$" *.txt`
conversely, the dollar `$` character in regexp means "end of the line" and will only match things that are just before the end
#####  `egrep -r "this|that" *` 
the pipe `|` character inside a regexp means "or" and in this example will match either "this" or "that"

---

# thats it
you know everything about grep now 