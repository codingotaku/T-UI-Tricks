# T-UI-Tricks
Some tricks that I found while using [T-UI ConsoleLauncher](https://github.com/fAndreuzzi/TUI-ConsoleLauncher) and [Termux](https://github.com/termux/termux-app)

## Using Termux Commands inside T-UI
Even though there is a [TUI-Expert](https://github.com/v1nc/TUI-Expert) + [Termux Exported](https://github.com/v1nc/termux-app/) available for this,  
if you are rooted then export Termux user bin folder into the PATH from T-UI

```bash
export PATH=$PATH:/data/data/com.termux/files/usr/bin/
```
and type in `su` to get sudo access  
now you can use all commands of Termux bin folder from T-UI and profit.

This needs to be done for every session like if TUI app re-launchs or the phone is rebooted etc..
so you can just add an alias called init as failsafe.

```bash
alias --add init=export PATH=$PATH:/data/data/com.termux/files/usr/bin/:/data/data/com.termux/files/usr/bin/applets
```

If T-UI can be configured to run commands after boot then this would be close to what everyone wants.
(it may not be fool proof, but I like the idea of accessing termux commands from everywhere)

##### cons
you cannot use any terminal apps like calcurse, vi/vim, nano, etc.. or apt since it will run as root user after `su` command.  
In a nutshell anything that needs stdout as a terminal will have problem running on T-UI.

## Add shortcut to webpages
In normal launchers you can add shortcut to web pages which almost all browsers supports.  
but T-UI has alias, you can create an alias to open web pages with

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
