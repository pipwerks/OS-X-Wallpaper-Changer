OS-X-Wallpaper-Changer
======================

Applescript for changing the Mac OS X desktop picture based on the time of day and the season

- Perceval FARAMAZ, November 2013 (for this version)
- Forked from : https://github.com/pipwerks/OS-X-Wallpaper-Changer
- MIT license

##What it does
This is an AppleScript that changes your Mac's desktop picture based on the time of day.  The day is split into six 'periods':

- Morning Early (12:01am - 8:00am)
- Morning Late (8:01am - 12:00pm)
- Afternoon Early (12:01pm - 3:00pm)
- Afternoon Late (3:01pm - 6:00pm)
- Evening Early (6:01pm - 9:00pm)
- Evening Late (9:01pm - 12:00am)

And 4 season :
- Winter (Jan-Feb-Mar)
- Spring (Apr-May-Jun)
- Summer (Jul-Aug-Sep)
- Fall (Oct-Nov-Dec)

Each period has a corresponding folder, which is meant to store images that evoke the period in question.

    /Users/{Username}/Pictures/Wallpapers/{Season}/{Time of day}/image.jpg

**The script will randomly select an image from the corresponding folder.** The image can be in any supported file type, including JPG, GIF and PNG images.

##How to use it

###Folder structure
If you choose to use the default settings, all you need to do is create folders in your `Pictures` folder that correspond to the following sample paths:

- `~/Pictures/Wallpapers/Winter/Morning Early/`
- `~/Pictures/Wallpapers/Winter/Morning Late/`
- `~/Pictures/Wallpapers/Winter/Afternoon Early/`
- `~/Pictures/Wallpapers/Winter/Afternoon Late/`
- `~/Pictures/Wallpapers/Winter/Evening Early/`
- `~/Pictures/Wallpapers/Winter/Evening Late/`
And so on for each season.
OR you can download the folder named "Wallpaper" (scroll up).

###Images
You must supply your own images. Personally, I downloaded images from NationalGeographic.com, which provides high quality free wallpaper images. http://ngm.nationalgeographic.com/wallpaper/download
 
###Script file
This script file itself can be located anywhere.

The script must be run at specified intervals using automation of some kind. I use GeekTool, but you may also use a built-in service such as crontab. 


##Customization
This script can be freely customized. It is heavily commented to make it easy to understand. For example, you can easily change the specified times of day or folder names by editing the script. You can simplify to something such as "day" and "night", or get even more granular and specify a custom folder for each hour of the day.

###Multiple monitors
The script includes support for multiple monitors. By default, it will display the same image on all monitors. If you prefer to set a unique image on each monitor, set the `useSamePictureAcrossDisplays` variable to `false`. 
