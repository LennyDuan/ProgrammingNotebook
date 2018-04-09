## Use Alias and Function 
Alias & bash function is a good way to shorter your command line. If you have a very long command line or need to do multiple task at the same time. Try to use __alias__ and __function()__ to save your times.

### Example to use alias & function: 
#### 1. Do __git__ add & commit & push with same message _new changes_ to __master__
##### Example:
* Input `gitnew` in a bash shell: 
```
hongyiduan $ ~: gitnew
```

* Bash shell will run 3 commands:
```
hongyiduan $ ~: git add.
hongyiduan $ ~: git commit -m'new changes'
hongyiduan $ ~: git push origin
```

##### Step:
* Create `~/.bash_profile` via command line `> ~/.bash_profile`
* Edit this file via `vim` (whatever you want) with these `code`:
```
alias gitnew='git add . && git commit -m'new changes' && git push origin'
```
* Save the changes and open an __new__ shell
* Enjoy the colorful command result.