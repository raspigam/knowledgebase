# Downsampling images

1. Open a terminal
2. Find the path to your source image file
3. Given source image file img.jpg in the current directory and a desired output image width of 1024 pixels, named "img-1024.img", execute
```
convert img.jpg -filter Lanczos -sampling-factor 1x1 -unsharp 1.5x1+0.7+0.02 -quality 90 -resize 1024 img-1024.jpg
```

Alternatively, if e.g. all jpg files in a directory need to be converted in-place (output replaces input file), execute
```
mogrify -filter Lanczos -sampling-factor 1x1 -unsharp 1.5x1+0.7+0.02 -quality 90 -resize 1024 *.jpg
```

Source:
* http://www.imagemagick.org/Usage/resize
* https://www.dpreview.com/forums/post/40282142
