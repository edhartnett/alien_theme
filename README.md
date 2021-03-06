# alien_theme

This is a theme for GRUB2.

# Final Results

![Alt text](screenshot.png?raw=true "Screenshot")

# Help for Mere Earthlings

A good guide can be found here:
<pre>
http://wiki.rosalab.ru/en/index.php/Grub2_theme_tutorial
</pre>

## Making Fonts

For grub2, convert a ttf (or some other allowed font files) like this:

<pre>
grub2-mkfont tokyodrifterstaightexpand.ttf -v --bold --size 24 --range=0x0-0x7f  -o /boot/grub2/themes/alien_theme/alien_big.pf2
</pre>

## Regenerating GRUB2 Config File

Some theme changes require the regeneration of the GRUB2 config file.

<pre>
grub2-mkconfig -o /boot/grub2/grub.cfg
</pre>

## Icons

Icons in the icon directory have the same name as the
--class=CLASSNAME in the grub.cfg menu entry.

## Contents of /etc/default/grub

<pre>
GRUB_TIMEOUT=57
GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
GRUB_DEFAULT=saved
GRUB_CMDLINE_LINUX="rd.lvm.lv=fedora/swap rd.md=0 rd.dm=0 vconsole.keymap=us $([ -x /usr/sbin/rhcrashkernel-param ] && /usr/sbin/rhcrashkernel-param || :) rd.luks=0 vconsole.font=latarcyrheb-sun16 rd.lvm.lv=fedora/root rhgb quiet"
GRUB_THEME="/boot/grub2/themes/alien_theme/theme.txt"
GRUB_FONT=/boot/grub2/fonts/unicode.pf2
GRUB_GFXMODE=1280x800
GRUB_GFXPAYLOAD_LINUX=keep
GRUB_INIT_TUNE="480 440 4 440 4 440 4 349 3 523 1 440 4 349 3 523 1 440 8 659 4 659 4 659 4 698 3 523 1 415 4 349 3 523 1 440 8"
</pre>

# Fun?

This is not about fun! This is about preparing for the eventual
invasion of Earth by another species.

