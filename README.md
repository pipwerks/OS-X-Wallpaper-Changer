# This script is no longer supported, and is no longer necessary. Repo is in read-only mode
Starting with Mojave in 2018, macOS natively supports dynamic wallpapers. Here is a good article outlining how to rotate your custom wallpaper images with no scripting required. https://appleinsider.com/articles/18/10/01/how-to-create-your-own-dynamic-desktops-in-macos-mojave

# OS-X-Wallpaper-Changer

Applescript for changing the Mac OS X desktop picture based on the time of day

- Philip Hutchison, April 2013
- http://pipwerks.com
- MIT license http://pipwerks.mit-license.org/

## What it does
This is an AppleScript that changes your Mac's desktop picture based on the time of day.  The day is split into six 'periods':

- Morning Early (12:01am - 8:00am)
- Morning Late (8:01am - 12:00pm)
- Afternoon Early (12:01pm - 3:00pm)
- Afternoon Late (3:01pm - 6:00pm)
- Evening Early (6:01pm - 9:00pm)
- Evening Late (9:01pm - 12:00am)

Each period has a corresponding folder, which is meant to store images that evoke the period in question. For example, you could have a picture of a sunset in the "Evening Early" folder, or a picture of the moon in the "Evening Late" folder.

    /Users/YOUR_USER_NAME/Pictures/Wallpapers/Time of Day/Evening Early/sunset.jpg
    /Users/YOUR_USER_NAME/Pictures/Wallpapers/Time of Day/Evening Late/moon.jpg

**The script will randomly select an image from the corresponding folder.** The image can be in any supported file type, including JPG, GIF and PNG images.

## How to use it

### Folder structure
If you choose to use the default settings, all you need to do is create folders in your `Pictures` folder that correspond to the following sample paths:

- `~/Pictures/Wallpapers/Time of Day/Morning Early/`
- `~/Pictures/Wallpapers/Time of Day/Morning Late/`
- `~/Pictures/Wallpapers/Time of Day/Afternoon Early/`
- `~/Pictures/Wallpapers/Time of Day/Afternoon Late/`
- `~/Pictures/Wallpapers/Time of Day/Evening Early/`
- `~/Pictures/Wallpapers/Time of Day/Evening Late/`

### Images
You must supply your own images. Personally, I downloaded images from NationalGeographic.com, which provides high quality free wallpaper images. http://ngm.nationalgeographic.com/wallpaper/download
 
### Script file
This script file itself can be located anywhere. I keep mine in the `/Pictures/Wallpapers/Time of Day/` folder.

The script must be run at specified intervals using automation of some kind. I use GeekTool, but you may also use a built-in service such as crontab. 

http://developer.apple.com/library/mac/#documentation/Darwin/Reference/ManPages/man1/crontab.1.html

I instruct GeekTool to execute the script every 15 minutes (1800 seconds). Use this line in GeekTool's command field:

    osascript ~/Pictures/Wallpapers/Time\ of\ Day/wallpaper.scpt


## Customization
This script can be freely customized. It is heavily commented to make it easy to understand. For example, you can easily change the specified times of day or folder names by editing the script. You can simplify to something such as "day" and "night", or get even more granular and specify a custom folder for each hour of the day.

### Multiple monitors
The script includes support for multiple monitors. By default, it will display the same image on all monitors. If you prefer to set a unique image on each monitor, set the `useSamePictureAcrossDisplays` variable to `false`. 
