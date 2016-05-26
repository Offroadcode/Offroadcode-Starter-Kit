#Using the Starter Kit

##Things you need to have installed

Your local dev environment probably already has this stuff installed anyway but it might be worth checking if everything is there.

* Ruby
* Sass
* Node.js
* Grunt
* [Imagemagick](http://www.imagemagick.org/script/install-source.php)

##Grunt

We're currently using Grunt for our task management and there are some basic tasks set up in the `Gruntfile.js` config but you're welcome to add to them on a per project basis if you need other jobs doing beyond what's there. 

##Getting set up in your working directory / theme folder

Install the Grunt tasks we use so in command line/terminal cd to the project directory, and run `npm install`

It might also be prudent once everything is installed, to run `grunt devupdates` if you've not used this starter kit for a while. This will check for any updates to devDepenedencies and dependencies and advise which versions are current. 

Dev updates is currently set to just report what updates are available and not automatically update so if you do wish to update, edit the version numbers in the `package.json` file in the project root. 

##Grunt tasks

**JS Minify & Concatenation**

If you need to add new JS files to the project, simply drop them into `/js/app/` and Grunt will minify and concatenate everything.

You don't need to reference them in the HTML, Grunt will run the task and compile them all into `production.js` which is referenced at the bottom of your HTML template above the `</body>` tag.

For the time being, files in `/js/libs/` need referencing in HTML and are not processed in Grunt.

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

If you create any SVG assets for the project - icons etc, save them to /assets/images/svg/ and Grunt will generate a PNG version of the same size to use as a fallback in your CSS in conjunction with Modernizr class fallbacks.

If it doesn't work, install SVG2PNG - https://github.com/pascalduez/grunt-svg2png (npm install --save-dev pascalduez/grunt-svg2png)

**Autoprefixing CSS**

When Grunt is run, it runs through the main stylesheet/s and checks on whether selectors need vendor prefixing so write un-prefixed css and run grunt.

##Grunt Tasks

There's a couple of simple tasks to save you running everything each time. They are:

* `grunt` - Just compiles, autoprefixes and watches your sass
* `grunt build` - Compiles your sass, concatenates all your JS into a production file and builds Modernizr
* `grunt assets` - Generate favicons, image optimisation and run svg2png conversion
* `grunt devupdates` - Only need to run at the start of a new project to check if dependencies need updating

##Additional scripts

The starter kit does include a couple of scripts and scaffolds that I consider useful and have found common need for on projects so delete as necessary. They are:

* [https://github.com/WickyNilliams/headroom.js/](headroom.js) for the disappearing top header bar
* [https://github.com/christophery/pushy](Pushy) Off canvas navigation
* [http://cferdinandi.github.io/kraken/grid.html](Kraken Grids) for layout