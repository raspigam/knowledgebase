# Exporting SVG files to PNG format

E.g. when you have saved a Scratch 2 (online) project (`.sb2` file) you unzipped into a directory to get hold of the stage and sprite image files, you have to convert the sprite svg files to png files Scratch 1.4 can read.

The Inkscape app can come to the rescue without even opening a gui! It accepts command line parameters to not open the gui (`-z`) specify the svg file to export to png (`-e`) and use a specific dpi for the conversion to pixels (`-d`).

For instance, if you downloaded the Knock Knock project at https://scratch.mit.edu/projects/136902427/#editor (choosing `File` and then `Download to your computer`), unzipped the downloaded `.sb2` file into the directory `Scratch/Knock Knock` and would like to import sprite costume number 1 into Scratch 1.4, you can issue:

```
$ inkscape -z -e Scratch/Knock\ Knock/1.png -d 90 Scratch/Knock\ Knock/1.svg
```
