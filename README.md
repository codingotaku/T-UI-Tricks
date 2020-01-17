# T-UI-Tricks
Some tricks that I found while using T-UI and Termux 

## Using Termux Commands inside T-UI
Even though there is a [TUI-Expert](https://github.com/v1nc/TUI-Expert) + [Termux Exported](https://github.com/v1nc/termux-app/) available for this,  
if you are rooted then export Termux user bin folder into the PATH from T-UI

```bash
export PATH=$PATH:/data/data/com.termux/files/usr/bin/
```
and type in `su` to get sudo access  
now you can use all commands of Termux bin folder from T-UI and profit.

This needs to be done for every session (when you restart)
so you can just add an alias called init 

```bash
alias --add init=export PATH=$PATH:/data/data/com.termux/files/usr/bin/
```
## Add shortcut to webpages
In normal launchers you can add shortcut to webpages which almost all browsers supports.  
but T-UI has alias, you can create an alias to open webpages with

```bash
alias --add browse=am start -a android.intent.action.VIEW -d https://% --user 0
```

Now you can just add aliases like

```bash
alias --add github=browse anilist.co
```
and profit.

##### note
if you use `http://` instead of `https://` sometimes you don't have to type in the whole address (depends on browser),  
and has some other profits you get. But I preffer `https://` than `http://` so I'm gonna leave it there.

