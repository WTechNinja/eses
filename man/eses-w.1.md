% ESES-W(1) eses-w 
% WTechNinja, kaonkaon
% April 2022

# NAME
eses-w - Screenshot script for wayland, with QR Scanner feature

# SYNOPSIS
**eses-w** [OPTION]

	
# DESCRIPTION
Basic screenshot script for wayland, with QR Scanner feature. Good for screenshot keybindings. It should be noted that the cursor isn't included in screenshots.
Has four different modes, selectable via options.

# OPTIONS
**--whole**
: Screenshot whole screen (without cursor) and save it as a file in your desired folders (set it yourself by changing the scripts)

**--select**
: Screenshot selected area / selected window, and save it as a file

**--whole_cp**
: Screenshot whole screen (without cursor) and put it on clipboard without saving (save your precious Kb in your HDD/SSD)

**--select_cp**
: Screenshot selected area / selected window, and put it on clipboard, then run QR code magic. 

# EXAMPLES
**eses-w --select_cp**
: Screenshot selected area to clipboard, then run QR code magic.

**eses-w --whole**
: Screenshot whole screen, and save as file.

# BUGS
https://github.com/WTechNinja/eses-w

