# Apps Guide

## Installing software (apps)

Raspbian, the operating system we use on the Raspberry Pi, comes with a lot of applications already installed ("built-in"), and
when you need to install an application that is not already there, you can most often easily install it using the `apt` command.
For instance if you would like to install an audio recording and editing application, and you found that an app called Audacity
is well suited for use on the Raspberry Pi, you can install it as follows:

* we need to ensure the Raspberry Pi can connect to the internet; please refer to our [Getting online](/guides/getting-online)
  guide
* open the top-left Raspberry menu by clicking on it
* select (click) Accessories
* select the Terminal menu item to open the Terminal app
* a window will open showing an empty screen with a single line on it e.g. `pi@my-pi-computer:~ $`
* to update the app package list and get the latest updates, type `sudo apt update` and press "enter" (this is only needed once
  when installing multiple apps)
* type `sudo apt install audacity` and press "enter" to install Audacity
* you can find Audicity in the Raspberry menu when you select the section "Sound & Video"

## Removing software (apps)

Removal of sofware works similarly, only now the command is e.g. `sudo apt remove audacity` (`remove` instead of `install`) if
you'd like to remove the Audacity application.

## Updating software (apps) and the operating system

It is recommendable to regularly (depending on connectivity, let's say once per week) check for updates and install them, as
in this way your system keeps its security high by having all recent security patches applied.

* open up a Terminal as explained in the Installing software section above
* type `sudo apt update` and press "enter" to get the latest list of software updates
* type `sudo apt upgrade` and press "enter" to install the updates

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
