# easierassets — fork of (https://github.com/YEDev/easyassets)

## What you will need

1. Homebrew: ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
2. librsvg: brew install librsvg
3. pngquant: brew install pngquant
4. imagemagick: brew install imagemagick --with-librsvg

### How it works:

1. Clone this repository and place the easyassets.rb file in a directory where you would like to generate
your image assets.
2. Install librsvg, pngquant, and imagemagick via [homebrew](http://brew.sh/)
3. Add your SVG file(s) to the directory. We recommend creating a 320 by 480 pixel canvas and placing the image in it.
_The allows the graphic designer to see how the image would be placed on a small Android or old iPhone screen. Don't worry,
the extra whitespace will be trimmed for the final result._
4. You should now have a directory that with contents similar to this:
![directory](http://i.imgur.com/OKe0NQd.png)
5. Open a terminal and cd into the working directory.
6. Make sure that you have the "execute" permission set for easyassets.rb
  * You can do this with `sudo chmod 755 easyassets.rb`
7. Run `./easyassets.rb [image].svg`
  * You can also run `/easyassets.rb [image].svg [initial-width] [initial-height]`
    * The provided dimensions should be the desired size of the image as if the SVG was used on an mdpi 320dp-wide screen,
or an iPhone 1/3/3GS screen.
  * Multiple images can be passed to the script like so: `./easyassets.rb [image1].svg [image2].svg` or `/easyassets.rb *.svg`
8. You will see a lot of text scrolling by in your terminal window. It will look something like this:
![executing](http://i.imgur.com/XGTKAW7.png)
9. You should now have plenty of directories inside your working directory, each containing the proper size of the image(s)
for the screen resolutions and densities.
![result](http://i.imgur.com/yur6Dek.png)
10. Copy the `drawable-` directories to your `res` directory in your Android project.

Here is an example of a drawable-mdpi and a drawable-xxhdpi image:
![mdpivsxxhdpi](http://i.imgur.com/q9Hpwgb.png)

### Enjoy!
