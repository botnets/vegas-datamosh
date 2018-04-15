# vegas-datamosh ![Github All Releases](https://img.shields.io/github/downloads/delthas/vegas-datamosh/total.svg?style=flat-square)
**A pack of Sony/MAGIX Vegas Pro scripts for YTP (datamoshing, multilayering, ...), using FFmpeg and Avidemux**

## Setup
Download the latest [release](../../releases/) **(the windows64.zip file)** and unpack it into your ```C:\Users\<user>\Documents\Vegas Script Menu``` folder. (If the folder does not exist, create it.)

Several entries will be added in the ```Tools -> Scripting``` submenu in Vegas. For each script, there will two entries, one of which is suffixed by "14" (for example, Datamosh and Datamosh14). If you use Sony Vegas <= 13, use the normal ones (eg Datamosh), otherwise use the ones suffixed by 14 (eg Datamosh14).

You can add scripts as toolbar buttons rather than having to click inside the ```Tools -> Scripting``` submenu, by adding them to the toolbar using the ```Options -> Customize Toolbar``` menu.

**If Sony/MAGIX Vegas complains about not finding the Microsoft.WindowsAPICodePack.dll file, simply restart Vegas and it will work. It just happens from time to time and I don't know how to fix it yet.**

**If you encounter any issue with the scripts, or you have any suggestion, please open an issue on this repository or contact me on Discord at ```cc#6439```.**

## Scripts

### Datamosh
This repeats N P-frames M times. N is the ```Frame count```, M is the  ```Frame repeats```.

To use, make a selection in the timeline using I and O, then it will be rendered and datamoshed and added to your project, all in one click. It can take quite some time for long selections so wait if Vegas seems to freeze.

The start of the selection is the first P-frame that will be repeated. The P-frame will be relative to the previous frame, which will be rendered as an I-frame. So for best results, the start of the selection should be a frame with a lot of movement.

The end of the selection simply tells the script until which frame it should rendered the datamoshed file. The longer the selection, the longer the render time.

### Layer
This does multilayering, by copying the select video clip/event N times, each time offsetting the clip by M frames. N is the ```Layer count```, M is the  ```Layering offset```. You can also choose to automatically render the multilayered clip by checking the ```Render``` hitbox, otherwise the copies clips will simply be added to the timeline.

To use, select a single video clip/event, then it will be multilayered automatically, and rendered transparently if specified.

*You can use a negative offset (eg -2 instead of 2), in which case the newest clips/events will be added at the back, instead of the front of the previous events.*

**If you choose to render automatically, the rendered file will support alpha/transparency, meaning you don't need to add a green screen and remove it after, the alpha is handled automatically.**

### Render
This simply renders a part of the timeline and places it into the timeline in a single click.

To use, make a selection in the timeline using I and O, then it will be rendered and added to your project, all in one click.

**The rendered file will support alpha/transparency, meaning you don't need to add a green screen and remove it after, the alpha is handled automatically.**

## Tips
*On most script window prompts, pressing ```enter``` confirms and pressing ```space``` toggles the checkbox (if present) so you don't even need to use your mouse most of the times.*

## License
All the code is licensed under MIT. The releases include binaries of FFmpeg and Avidemux and the Xvid codec, which are under the LGPL+GPL and GPL and GPL licenses respectively.
