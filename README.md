# eses-w
Screenshot script with QR Scanner feature (Forked from [u/LithiumFrost](https://www.reddit.com/r/unixporn/comments/p0md2y/oc_scan_a_qr_code_with_a_keyboard_shortcut/) [Codes](https://github.com/jayden-chan/dotfiles/blob/7f4ab0257604a52b3f5befe73cf21a5f95a19f54/scripts/screenshot.sh#L13) and then forked again from [kaonkaon/eses](https://github.com/kaonkaon/eses) to add wayland support.)

### Name Meaning
How you pronounce "SS"? yeah. And then add a `-w` for wayland.

### Description
Basic screenshot script for wayland, with QR Scanner feature. Good for screenshot keybindings.
It should be noted that the cursor isn't included in screenshots.

### Function
* --whole
	* Screenshot whole screen and save it as a file in your desired folders (set it yourself by changing the config)
* --select
	* Screenshot selected area / selected window, and save it as a file
* --whole_cp
	* Screenshot whole screen (without cursor) and put it on clipboard without saving (save your precious Kb in your HDD/SSD)
* --select_cp
	* Screenshot selected area / selected window, and put it on clipboard
		* if there's a QR Code detected in the pictures, it will try to scan it
			* if it fails, it will leave the screenshot copied on the clipboard
			* if it succeeds, the user will be prompted to copy either the image or scanned result
			 ![Dialog](https://github.com/WTechNinja/eses-w/blob/main/me%20when%20dialog.png?raw=true)
			 
### Configuration
All of the default configuration is in the beginning of the `eses-w` script with plenty of comments, and it will likely change.
As of writing this, the default config is:

```
# Notification title when grim successfully saved
succ_noTit="Kasha!"

# Notification text when grim successfully saved
succ_noTex="Screenshot saved!"

# Notification text when grim successfully saved
succ_noTex_cp="Screenshot copied to clipboard!"

# Notification title when QR Scanned and copied
succ_noTit_sccop="QR Code scan result"

# Prompt dialog title when qr code scanned
dia_tit="Prompt"

# Prompt dialog text when qr code scanned
dia_tex="QR Code detected, and sucessfully scanned\n Do you want to copy the scan result instead?"

# Prompt dialog copy image button
dia_imgcop_butt="Copy image"

# Prompt dialog copy image button
dia_sccop_butt="Copy scan result"

# grim save dir
sv_dir="/home/$USER/Pictures/Screenshots/"

# grim file name
sv_name="$(date)"
```

### Dependencies
```
* zenity
* maim
* imagemagick
* xclip
* zbarimg
* notify-send
```

### Install
just copy it to executable path and make it executable and boom 

##### Using Clone (on /usr/local/bin)
```
cd /tmp
git clone https://github.com/WTechNinja/eses-w.git
cd eses-w
sudo mv eses-w /usr/local/bin/
chmod +x /usr/local/bin/eses-w
```
##### Using WGET (on /usr/local/bin)
> man page not included, download it yourself
```
wget https://raw.githubusercontent.com/WTechNinja/eses-w/main/eses-w
sudo mv eses-w /usr/local/bin/
chmod +x /usr/local/bin/eses-w
```
##### Rewrite the thing (when Copy Paste is bloat)
```
open your favorite text editor
write the entire thing
save
put it in random folder
make it executable
profit
```

#### Building the man page
> dependencies: pandoc, gzip

`eses-w.1.md` is just a markdown file, feel free to edit it to your liking and then, while in the `man` folder run;
```
pandoc eses-w.1.md -s -t man -o eses-w.1	
gzip eses-w.1 -c > eses-w.1.gz
```
then the generated `eses-w.1.gz` file can be installed in `/usr/local/man/man1`  
```
# Make /usr/local/man/man1 if it doesn't already exist
sudo mkdir -p /usr/local/man/man1
sudo mv eses-w.1.gz /usr/local/man/man1/
sudo mandb
```
After that, you can use `man eses-w` to view the man page.

#### Config File
upon first run, the config file will be generated under `/home/$USER/.config/eses-w/`

The script will automatically generate the directory and config file with default configuration inside if theres no config directory and/or config file. no worry i get you 


## Contribute
I'm open to contributions, but you should contribute upstream at [kaonkaon/eses](https://github.com/kaonkaon/eses) Because I took the vast majority of this code from him. (ofc he's always welcome to copy things back from here anyway, but yeah)
