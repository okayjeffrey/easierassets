# easyassets

Mobile developers face many challenges, including making sure that a mobile application
looks great no matter which device it is installed on. Have you ever had a difficult time
making sure that your image assets are of a perfect size at all screen resolutions and pixel densities?

At [YouEye](https://www.youeye.com), we recently released our first mobile application, [YouEye for
Participants](https://play.google.com/store/apps/details?id=com.youeye.recorders.android.web).
The image below contains screenshots of the splash screen of the application running on
a Nexus 10, a Nexus 7, and a Samsung Galaxy S4. Can you spot the problem? We could and we
didn't like it.

![problem](http://i.imgur.com/mmJDEmM.png)

Presenting easyassets, a script for easily generating multiple sizes of image assets for Android and iOS.
Anyone who works with vector images will appreciate this tool, which can be described as a
[SVG](http://en.wikipedia.org/wiki/Scalable_Vector_Graphics) to
[PNG](http://en.wikipedia.org/wiki/Portable_Network_Graphics) image asset converter for major mobile
device's screen sizes and densities.

Please note that the script is licensed under the [GPLv3](http://www.gnu.org/copyleft/gpl.html).

### How it works:

1. Simply clone this repository and place the easyassets.rb file in a directory where you would like to generate
your image assets.
2. Make sure you have Ruby installed
3. Install librsvg and imagemagick via [homebrew](http://brew.sh/) or [apt](https://help.ubuntu.com/community/AptGet/Howto).
4. Add your SVG file(s) to the directory. We recommend creating a 320 by 480 pixel canvas and placing the image in it.
The allows the graphic designer to see how the image would be placed on a small Android or old iPhone screen. Don't worry,
the extra whitespace will be trimmed for the final result.
5. You should now have a directory that with contents similar to this:
![directory](http://i.imgur.com/OKe0NQd.png)
6. Open a terminal and cd into the working directory.
7. Make sure that you have the "execute" permission set for easyassets.rb
  * You can do this with `sudo chmod 755 easyassets.rb`
8. Run `./easyassets.rb [image].svg`
  * You can also run `/easyassets.rb [image].svg [initial-width] [initial-height]`
    * The provided dimensions should be the desired size of the image as if the SVG was used on an mdpi 320dp-wide screen,
or an iPhone 1/3/3GS screen. This option should only be used if your SVG does not have the correct size for these screens.
  * Multiple images can be passed to the script like so: `./easyassets.rb [image1].svg [image2].svg` or `/easyassets.rb *.svg`
9. You will see a lot of text scrolling by in your terminal window. It will look something like this:
![executing](http://i.imgur.com/GWsy1Jb.png)
10. You should now have plenty of directrories inside your working directory, each containing the proper size of the image(s)
for the screen resolutions and densities.
![result](http://i.imgur.com/yur6Dek.png)
11. Copy the `drawable-` directories to your `res` directory in your Android project.

Here is an example of a drawable-mdpi and a drawable-xxhdpi image:
![mdpivsxxhdpi](http://i.imgur.com/q9Hpwgb.png)

### Enjoy!
