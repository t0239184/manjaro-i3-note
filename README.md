# Manjaro i3 Note
###### tags: `Manjaro` `i3`

## Install Pinyin input method
Install google pinyin input method

```shell=
pacman -S fcitx-googlepinyin fcitx-im fcitx-configtool opencc
```

```shell=
➜  ~ cat .xprofile
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIRS=''@im=fcitx''

```

open ``fcitx-configtool``
-> input method panel
-> +
-> disable ``only show ...``
-> search ``pinyin``
### Some config file not found
~/.bashrc, ~/.xinitrc , .xprofile is not found can create it.


## Font
pacman -S noto-fonts-cjk

## Termial
pacman -S lilyterm
lilyterm -p > .config/lilyterm/lilyterm.rc

## Switch ctrl and capslock
touch ~/.Xmodmap
vim ~/.Xmodmap
```
!
! Swap Caps_Lock and Control_L
!
clear lock
clear control
add control = Caps_Lock Control_L Control_R
keycode 66 = Control_L Caps_Lock NoSymbol NoSymbol
```
> man xmodmap

touch .xinitrc && vim .xinitrc 
```
# Remaping keyborad with user custom file
if [ -f $HOME/.Xmodmap ]; then
    /usr/bin/xmodmap $HOME/.Xmodmap
fi

```

## add non latin language use font

/etc/fonts/conf.d/65-nonlatin.conf
```
<description>Set preferable fonts for non-Latin</description>
<alias>
 <family>serif</family>
 <prefer>
  <family>Artsounk</family> <!-- armenian -->
  ...
  <family>Noto Serif CJK TC</family> <!-- cjk -->
  <family>MS Mincho</family> <!-- han (ja) -->
  <family>SimSun</family> <!-- han (zh-cn,zh-tw) -->
  ...
 </prefer>
</alias>
```

/etc/fonts/conf.d/60-latin.conf


>https://medium.com/@archerindigo/manjaro%E5%AD%97%E5%9E%8B%E8%A8%AD%E5%AE%9A%E6%8A%98%E9%A8%B0%E8%A8%98-%E4%B8%8A-b0483784b03e

## apper
lxappearance

## FireFox
### Fullscreen dont hide tab and menu bar
about:config
browser.fullscreen.autohide = false

## File manager
Thunar

## Image viewer
ristretto
tumbler

## i3 config
vim ~/.config/i3/conf
change font to Noto Sans CJK TC Reqular 10

