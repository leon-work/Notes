# Latex

## Tikz / Pgfplot

### [Flowcharts](https://www.overleaf.com/learn/latex/LaTeX_Graphics_using_TikZ:_A_Tutorial_for_Beginners_(Part_3)%E2%80%94Creating_Flowcharts)
1. 模板

   ```latex
   \tikzstyle{start} = [rectangle, rounded corners, minimum width=3cm, minimum height=0.5cm,text centered, draw=black, fill=red!30]
   
   \tikzstyle{io} = [trapezium, trapezium left angle=70, trapezium right angle=110, minimum width=3cm, minimum height=1cm, text centered, draw=black, fill=blue!30]
   
   \tikzstyle{pro} = [rectangle, mminimum width=3cm, minimum height=0.5cm, text centered, draw=black, fill=orange!30]
   \tikzstyle{dec} = [diamond, minium width=3cm, minimum height=0.5cm, text centered, draw=black, fill=green!30]
   
   \tikzstyle{arrow} = [thick,->,>=stealth]
   
   \node(des1)[left of=p3,xshift = -2.5cm,align=left] {Black Box\\20hrs/simulation}; # 左对齐
   ```

   

### [Basics](https://www.overleaf.com/learn/latex/LaTeX_Graphics_using_TikZ:_A_Tutorial_for_Beginners_(Part_1)%E2%80%94Basic_Drawing)

### 3D plot
```latex
\addplot3 [contour gnuplot = {labels = false} ]{sin(deg(x))+cos(deg(y))}   # deg(x)
```

### Notes

1. [水平间距](www.ctex.org/documents/latex/graphics/node31.html)
    LATEX 在排列图形的时候实际上与排列其它的像文字这样的对象是一样的， 了解到这一点很重要。举例来说，如果行尾不是以 % 结束的话， LATEX 会 自动在两行之间加进一个字符的水平间距.
2.  单栏 8.3cm, 双栏 17.6cm; 单栏 3.26 inch, 双栏 6.52 inch
3. 12pt Articel: textwidth: 5.39749in, 13.70499cm  



# [Texlive](https://www.tug.org/texlive/quickinstall.html)

## [How to Remove](https://tex.stackexchange.com/questions/95483/how-to-remove-everything-related-to-tex-live-for-fresh-install-on-ubuntu)

```shell
sudo apt-get purge texlive*
sudo rm -rf /usr/local/texlive/* and rm -rf ~/.texlive*
sudo rm -rf /usr/local/share/texmf
sudo rm -rf /var/lib/texmf
sudo rm -rf /etc/texmf
sudo apt-get remove tex-common --purge
rm -rf ~/.texlive

find -L /usr/local/bin/ -lname /usr/local/texlive/*/bin/* | xargs rm
```



## [How to install](https://stone-zeng.github.io/2018-05-13-install-texlive-ubuntu/)

## Post-install: Setting PATH

```shell
gedit ~/.bashrc   
# 在最后添加
export PATH=/usr/local/texlive/2018/bin/x86_64-linux:$PATH
export MANPATH=/usr/local/texlive/2018/texmf-dist/doc/man:$MANPATH
export INFOPATH=/usr/local/texlive/2018/texmf-dist/doc/info:$INFOPATH
source ~/.bashrc  #更新
# 保证sudo模式下路径仍然可用
sudo visudo
# 找到
' secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
'
# 在前面添加texlive路径
secure_path="/usr/local/texlive/2018/bin/x86_64-linux:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"

# 检查
tlmgr -v
pdftex -v
xetex -v
luatex -v
sudo cp /usr/local/texlive/2019/texmf-var/fonts/conf/texlive-fontconfig.conf /etc/fonts/conf.d/09-texlive.conf
```

### Check the platform

```shell
arch
```



# [Texstudio](https://code.launchpad.net/~sunderme/+archive/ubuntu/texstudio)

```shell
sudo add-apt-repository ppa:sunderme/texstudio
sudo apt-get update
sudo apt-get install texstudio
```

## Macros

```Texstudtio
%SCRIPT
txt = cursor.selectedText()
editor.write("\\boldsymbol{"+txt+"}")
cursor.clearSelection()
```

![Screenshot from 2019-10-21 20-49-06](/home/leon/Pictures/Screenshot from 2019-10-21 20-49-06.png)

## Latexindent

```shell
sudo cpan Log::Log4perl
sudo cpan Log::Dispatch::File
```



