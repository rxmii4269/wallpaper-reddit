# NOTICE  
This was a fork from https://github.com/markubiak/wallpaper-reddit - I have updated the Mac OS section to be compatible with the latest versions. I will also be expanding Linux documentation. 

## How-To Guide located with @ https://christitus.com/change-wallpaper/

# Extra Commands not in guide

## Overlay Titles
The program has an option to overlay the title of the image directly onto the image itself, so using conky to constantly read the title of the image from `~/.wallpaper/title.txt` is no longer necessary (although it still works, and is recommended if not using the "resize" option).  This function is not enabled by default, but it can be enabled with either the `--settitle` command line flag or more permanently in the config under the `[Title Overlay]` section. There are five options for setting titles: size, x/y alignment, and x/y offset.  

### Overlay Title Configuration Options
Options for the overlay title can only be set in the config file.  They are under the [Title Overlay] section.
 - `titlesize` sets the font height at which the title will be rendered, in pixels.
 - `titlealignx` sets the horizontal alignment of the title, and can be either `left`, `center` or `right`.
 - `titlealigny` sets the vertical alignment, and can be `top` or `bottom`.
 - `titleoffsetx` and `titleoffsety` allow you to set an additional offset from the edge of the image, in pixels.

## Startup
If wallpaper-reddit is run with the `--startup` flag, the program will wait on an internet connection.   Once startup is activated, the script will try to connect to Reddit to download new wallpaper upon startup.  The default setting is an interval of 3 and 10 attempts, which means that the script will try to connect to Reddit every 3 seconds for up to 10 tries, giving a total of 30 seconds before the script gives up.  
### Startup Configuration Options
Options for the startup can only be set in the config file.  They are under the [Startup] section.
-  `interval` describes the amount of time, in seconds, between wallpaper-reddit's attempts to procure new wallpaper.
 - `attempts` describes the number of attempts that will be made to connect to Reddit. After this number of attempts has failed, wallpaper-reddit will cease to try downloading wallpaper during the current startup.  

## Saving
If wallpaper-reddit is run with the `--save` flag, no wallpaper will be downloaded.  The current wallpaper will be copied to the save directory, as specified in the config file (default is `~/Pictures/Wallpapers` on Linux, `~/My Pictures/Wallpapers` on Windows), and its title will be put into a titles.txt file inside the same directory.  

## Blacklists
There is a function to blacklist a certain wallpaper from the script if it is particularly ugly.  Simply run the script with the `--blacklist` flag.  The script will run as usual, but additionally blacklist your current wallpaper.  You'll get a new wallpaper and never see the old one again.  

## External commands and wallpaper info
Because more information is always better, much more than the wallpaper itself exists in `~/.wallpaper`.
- `blacklist.txt` contains the urls of blacklisted wallpapers, one can manually add urls without issue.
- `url.txt` is the url of the current wallpaper
- `title.txt` is the title of the current wallpaper (useful if you want to put the title into conky)
- `external.sh` is a bash script that is run at the end of every execution of the script (Linux only).  Any extra commands to deal with the wallpaper can be safely placed in this bash script.  I personally have mine darken my xfce4-panel if the wallpaper is too bright at the top, and set the wallpaper as my SLiM/xscreensaver background.

## Contact
If there is an issue with the program, please file a GitHub issue.  If you need more specific help troubleshooting a specific desktop or have an issue that isn't worthy of GitHub, feel free to reach out to me via email: mkubiak.dev at gmail dot com
