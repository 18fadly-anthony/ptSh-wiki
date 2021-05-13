You can find ptSh configuration file in `~/.config/ptSh/config`. 

## Escape codes
You can set colors and text decorations with [ANSI escape codes](https://en.wikipedia.org/wiki/ANSI_escape_code). Every escape code has some effect (foreground color, background color, underline, blinking etc.). You can list all escape codes and see their effects with this script:

```shell
for (( i=0; i<108; i++)) do
    echo -ne "\033[${i}m${i}\033[00m "
done
echo -e "\033[0m"
```
Correct ways to specify escape codes in config are `\x1B[Ym` and `\033[Ym`, where `Y` is escape code number (this from script output), e.g.: 

```shell
DIR_NAME_ESCAPE_CODES='\x1B[35m'          #sets foreground color of directory name to magneta
FILE_NAME_ESCAPE_CODES='\x1B[4m'          #sets underline for file names
LINK_NAME_ESCAPE_CODES='\x1B[5m\x1B[42m'  #makes hyperlink name blinking and green background color
```

## Restoring default configuration
Config file with default configuration is in `~/.local/share/ptSh/config`. To restore defaults, replace your config file with it:
```shell
rm ~/.config/ptSh/config
cp ~/.local/share/ptSh/config ~/.config/ptSh/config
```
**Do not edit default configuration file**