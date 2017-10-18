# Making screen shots

## Using `scrot`

* [Open a Terminal window](./open-terminal.md)
* For a screenshot of the whole screen
  * Type `scrot -d 15 -c ~/Pictures/screen\ %Y%m%d\ %H%M%S.png`
  * `scrot` will count down 15 seconds giving you the opportunity to switch windows to have the right content on screen
* For taking a screenshot of a smaller part of the screen
  * Type `scrot -s ~/Pictures/screen\ %Y%m%d\ %H%M%S.png`
  * `scrot` waits for you to select a rectangular region by clicking and holding the left mouse button while dragging to define the
    region that is screen shot, releasing the mouse button snaps the shot
* It seems that combining the region `-s` and countdown option `-d` does not work, so when you need the count down and don't want the whole screen to be shot, you have to capture a whole screen first and edit it afterwards with a picture editor, e.g. The Gimp
* You can find the captured screen shot in your `Pictures` directory, e.g. using the [File manager](./file-manager.md)
