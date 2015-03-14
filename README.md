ios2android
===========

A simple script to port iOS retina images to the appropriate Android density buckets.

Porting an iOS application to Android is a time-consuming task, especially when you have to manually resize 1000 images from iPhone/iPad dimensions to Android density buckets and screen sizes. This script aims to save as much time as possible by automatically resizing these images for you.


Prerequisites
-------------

[ImageMagick](http://www.imagemagick.org/script/binary-releases.php)

On Mac OS X, the easiest way to install ImageMagick is with [Homebrew](http://brew.sh/):

    brew install imagemagick


Usage
-----

1. Put the ios2android bash script somewhere in your path

2. Copy the retina iOS images you want to convert into an empty directory. 

3. From a terminal, cd into that directory and run:

```
$ ios2android
```


The script will evaluate each file in the directory, and determine if it is targeted for phone or tablet devices based on the filename. It will then create resized versions of the images and place them into the appropriately named density bucket folders. The script will also compensate for filenames that are not valid in android (such as images starting with numbers or containing hyphens).

Once the script is complete, simply copy the new folders into your Android project and you will have the equivalent of the iOS images. Way easier than manually scaling it yourself!

You can also create phone images directly from iPad images by specifying a scaling factor to use. Take a look at example 3 below.


Example
-------

1) A directory containing the following files:

```
intro_text@2x.png         (510 x 490 pixels)
```

will result in:

```
drawable-mdpi/intro_text.png          (255 x 245 pixels - 50%)
drawable-hdpi/intro_text.png          (383 x 368 pixels - 75%)
drawable-xhdpi/intro_text.png         (574 x 551 pixels - 112.5%)
```



2) iPhone 5 4" images are treated the same as iPhone for 3.5" images, so a directory containing the following files:

```
intro_text-568h@2x.png         (510 x 490 pixels)
```

will result in:

```
drawable-mdpi/intro_text.png          (255 x 245 pixels - 50%)
drawable-hdpi/intro_text.png          (383 x 368 pixels - 75%)
drawable-xhdpi/intro_text.png         (574 x 551 pixels - 112.5%)
```


License
-------

The MIT License (MIT)

Copyright (c) 2013 Ninjanetic Design Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


More Information
----------------


For more information on re-scaling iOS images to Android, you can find a great web tool here:

http://www.teehanlax.com/tools/density/


ios2android was created by Jason Adams of [Ninjanetic Design Inc.](http://www.ninjanetic.com)
