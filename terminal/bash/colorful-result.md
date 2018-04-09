## Colorful Command Result

To clear the result of a command line. If the command execute successfully, it will display __GREEN__ `Success` message. Otherwise, it will show __RED__ `Failed` message. 

#### Example:
![](/assets/colorful result.png)

#### Steps:
* Create `~/.bash_profile` via command line `> ~/.bash_profile`
* Edit this file via `vim` (whatever you want) with these `code`:
```
PROMPT_COMMAND=__prompt_command 
__prompt_command() {
        local EXIT="$?"
        local RED='\033[0;31m'
        local GREEN='\033[0;32m'
        if [ $EXIT != 0 ]; then
                echo -e "${RED}Failed"
        else
                echo -e "${GREEN}Success"
        fi
}
```