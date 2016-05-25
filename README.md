#Using the Starter Kit

##Things you need to install

It's assumed you've already got Ruby and Sass installed. If you haven't, get them installed first along with:

* Node.js and Grunt (see above)
* [Imagemagick](http://www.imagemagick.org/script/install-source.php)

##It's now Grunt powered

It's Grunt powered so you need to install Node.js and Grunt [Here are the getting started instructions](http://gruntjs.com/getting-started) or [some other install instructions](http://24ways.org/2013/grunt-is-not-weird-and-hard/).

##Getting set up in your working directory / theme folder

You will need to install the various Grunt tasks we use so in terminal cd to the project directory, and run `npm install`:

###The basic tasks it performs are:

**Minifies JS and then concatenates all the files into a single file**

If you need to add new JS files to the project, simply drop them into /js/app/ and Grunt does the rest.

You don't need to reference them in the HTML, Grunt will run the task and compile them all into production.js

For the time being, files in /js/libs/ need referencing in HTML and are not processed in Grunt.

**Image optimisation**

Any images located in /assets/images/ (jpg, png, gif) are automatically optimised and re-saved with the same name/paths when Grunt is run

**Sass compiling**

All files in /assets/sass/ are automatically compiled and minified and then output to /assets/css/screen.css which is referenced in the HTML

Do not under any circumstances edit /assets/css/screen.css, any changes you make will be lost next time Sass is compiled.

If you need to add a new scss file for some reason, you can do so by creating a _yourfilename.scss file (the underscore is needed) and you can then reference that in /assets/sass/screen.scss and it'll compile next time Grunt runs.

**CSS Prefixing**

You don't need to include browser specific prefixing for properties, they're automatically added when Grunt compiles the
Sass so just add un-prefixed properties and if they're needed it's taken care of.

**SVG fallbacks to PNG**

If you create any SVG assets for the project - icons etc, save them to /assets/images/svg/ and Grunt will generate a PNG version of the same size to use as a fallback in your CSS.

If it doesn't work, install SVG2PNG - https://github.com/pascalduez/grunt-svg2png (npm install --save-dev pascalduez/grunt-svg2png)

**Autoprefixing CSS**

When Grunt is run, it runs through the main stylesheet/s and checks on whether selectors need vendor prefixing so write un-prefixed css and run grunt.

**Favicon generation**

If you save a decent quality (ie. One that will scale down well) logo in /assets/images/ and call it favicon.png Grunt will generate Apple and Windows favicons for use and save them out with the relevant file names in the root directory of the site.

If it doesn't work, install Grunt Favicons- https://www.npmjs.com/package/grunt-favicons (npm install grunt-favicons --save-dev)

##Grunt Tasks

There's a couple of simple tasks to save you running everything each time. They are:

+ grunt - Just compiles, autoprefixes and watches your sass
+ grunt build - Compiles your sass, concatenates all your JS into a production file and builds Modernizr
+ grunt assets - Generate favicons, image optimisation and run svg2png conversion

**Some useful design scripts**

The starter kit does include a couple of scripts and scaffolds that I consider useful and have found common need for on projects so delete as necessary. They are:

[https://github.com/WickyNilliams/headroom.js/](headroom.js) for the disappearing top header bar
[https://github.com/christophery/pushy](Pushy) Off canvas navigation
[http://cferdinandi.github.io/kraken/grid.html](Kraken Grids) for layout