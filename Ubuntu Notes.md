# Ubuntu Notes
## [Sanpshot](https://itsfoss.com/take-screenshot-linux/)

**PrtSc** – *Save a screenshot of the entire screen to the “Pictures” directory.*
**Shift + PrtSc** – *Save a screenshot of a specific region to Pictures.*
**Alt + PrtSc** – *Save a screenshot of the current window to Pictures*.
**Ctrl + PrtSc** – *Copy the screenshot of the entire screen to the clipboard.*
**Shift + Ctrl + PrtSc** – *Copy the screenshot of a specific region to the clipboard.*
**Ctrl + Alt + PrtSc** – *Copy the screenshot of the current window to the clipboard*

## 删除

```bash
sudo apt-get autoremove  # 卸载残留软件包
nautilus  ~/.local/share/applications/  # 删除图标
nautilus  ~/.config/menus/applications-merged/
```

## Execute a .Run or .Bin file
.Run or .Bin files are probably the only file types you will ever need to mark as executable in normal use of Ubuntu. See [How to Execute](https://howtoubuntu.org/how-to-execute-a-run-or-bin-file-in-ubuntu).

```bash
chmod +x file-name.run
./file-name.run
```

## Desktop creation

```shell
sudo apt-get install --no-install-recommends gnome-panel
gnome-desktop-item-edit ~/Desktop/ --create-new
```

## [Add environment variable](https://blog.csdn.net/White_Idiot/article/details/78253004)

```shell
gedit ~/.bashrc 
export PATH=$PATH:/usr/local/MATLAB/R2017b/bin #add to start of PATH
export PATH=/path/to/your/dir:$PATH 	# add to end of PATH --- 
source ~/.bashrc 
```

# UEA VPN

```shell
$ f5fpc -s -t https://vpn.uea.ac.uk/ -x
$ f5fpc --info  (check)
$ f5fpc --stop   (disconnect)
```

# Google pinyin

```shell
sudo apt-get install fcitx fcitx-googlepinyin im-config
im-config
重启
```


# Anaconda

## Install non-conda package

```shell
Source activate myenv (myenv is the name of current enviroment)
pip install (name)
conda list (check if installed)
```

## Start Navigator

```shell
anaconda-navigator
```

## Notes

1. Before installing, in the terminal, go to the main folder. Then, run the command.

## Package error

> ​                              
>
> I'm not on MS Windows but I see several things in your screenshot
>
> 1. You are on base environment
> 2. You already have `spyder 3.3.3` and that means that you have to use `conda update spyder` or uninstall it and then install it with your command `conda install -c spyder-ide spyder=4.0.0b2`
> 3. The same with all remaining packages mentioned there (preferably one  by one since some may disappear like the kernel one when you uninstall  spyder 3.3.3)
> 4. If you see that Anaconda cannot find the package in your current channels, try via proposed channels on [Anaconda Cloud](https://anaconda.org/anaconda/repo) like `conda search --override-channels --channel URL/PACKAGE`
>
> Hope it helps (: 
>
> []: https://stackoverflow.com/questions/56817285/cant-update-spyder-to-4-0-0b2
>
> 


# Lyx

## [File 'xxx.sty' not found](https://wiki.lyx.org/FAQ/LaTeXErrors)

```shell
Kpsewhich <name> (kpsewhich ***.sty)
apt-file search ***.sty (Search the sty)
apt-get install texlive-latex-extra (Install the package)
texhash (Refresh tex)
>> Reconfigure in Lyx
```



# KILL Zombie

```shell
ps axo stat,ppid,pid,comm | grep -w defunct
sudo kill -9 3376
```

## [Install FONTS- chinese](https://zhuanlan.zhihu.com/p/40434062)

