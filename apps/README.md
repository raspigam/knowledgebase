# Apps

## Installing software (apps)

Raspbian, the operating system we use on the Raspberry Pi, comes with a lot of applications already installed ("built-in"), and
when you need to install an application that is not already there, you can most often easily install it using the `apt` command.
For instance if you would like to install an audio recording and editing application, and you found that an app called Audacity
is well suited for use on the Raspberry Pi, you can install it as follows:

* open the top-left Raspberry menu by clicking on it
* select (click) Accessories
* select the Terminal menu item to open the Terminal app
* a window will open showing an empty screen with a single line on it e.g. `pi@my-pi-computer:~ $`
* type `sudo apt install audacity` and press "enter" to install Audacity
* you can find Audicity in the Raspberry menu when you select the section "Sound & Video"

## Removing software (apps)

Removal of sofware works similarly, only now the command is e.g. `sudo apt remove audacity` (`remove` instead of `install`) if
you'd like to remove the Audacity application.

## Apps we use / recommend

### Chromium

Comes pre-installed on Raspbian.

### LibreOffice

Comes pre-installed on Raspbian.

### Scratch

Comes pre-installed on Raspbian.

### SonicPi

Comes pre-installed on Raspbian.

### FreeCAD

Install using `sudo apt install freecad`.

### Inkscape

Install using `sudo apt install inkscape`.

### GIMP

Install using `sudo apt install gimp`.

### Audacity

Install using `sudo apt install audacity`.
