# Using the Starter Kit

*Please note: While you're welcome to use this starter kit for your own projects, it comes as-is and we don't specifically offer support for it because it's an internal tool for our use. If you have any questions, please feel free to ask, we'll do our best to help but we can't guarantee a speedy response or solution :)*

## Things you need to have installed

Your local dev environment probably already has this stuff installed anyway but it might be worth checking if everything is there.

* Ruby
* Sass
* Node.js
* Grunt
* [Imagemagick](http://www.imagemagick.org/script/install-source.php)

## Grunt

We're currently using Grunt for our task management and there are some basic tasks set up in the `Gruntfile.js` config but you're welcome to add to them on a per project basis if you need other jobs doing beyond what's there. 

## Getting set up in your working directory / theme folder

Install the Grunt tasks we use so in command line/terminal cd to the project directory, and run `npm install`

It might also be prudent once everything is installed, to run `grunt devupdates` if you've not used this starter kit for a while. This will check for any updates to devDepenedencies and dependencies and advise which versions are current. 

Dev updates is currently set to just report what updates are available and not automatically update so if you do wish to update, edit the version numbers in the `package.json` file in the project root. 

## Grunt tasks

### JS Minify & Concatenation

If you need to add new JS files to the project, simply drop them into `/js/app/` and Grunt will minify and concatenate everything.

You don't need to reference them in the HTML, Grunt will run the task and compile them all into `production.js` which is referenced at the bottom of your HTML template above the `</body>` tag.

For the time being, files in `/js/libs/` need referencing in HTML and are not processed in Grunt.

### Image optimisation

Any images located in `/assets/images/` (jpg, png, gif) are automatically optimised and re-saved with the same name/paths when Grunt is run

Image optimisation will normally be handled by Umbraco / imagegen on the server but it's handy to run this command on any site assets that might not be uploaded and processed via the CMS.

### Sass compilation

All files in `/assets/sass/` are automatically compiled and minified and then output to `/assets/css/screen.css` which is referenced in the HTML

Do not under any circumstances edit `/assets/css/screen.css`, any changes you make will be lost next time Sass is compiled.

If you need to add a new scss file for some reason, you can do so by creating a `_yourfilename.scss` file (the underscore is needed) and you can then reference that in `/assets/sass/screen.scss` and it'll compile next time Grunt runs.

Any file created in `/assets/sass/` (including sub folders) is watched and compiled as long as you reference it in the `screen.scss` file.

### CSS Prefixing

You don't need to include browser specific prefixing for properties, they're automatically added when Grunt compiles the
Sass so just add un-prefixed properties and if they're needed it's taken care of.

### Autoprefixing CSS

You can edit `Gruntfile.js` to specify how many browser versions you want to support and provide autoprefixes for. It's just set for last 2 browser versions by default. 

## Grunt Tasks

There's a couple of simple tasks to save you running everything each time. They are:

* `grunt` - Just compiles, autoprefixes and watches your Sass while doing local dev
* `grunt build` - Compiles your Sass, concatenates all your JS into a production file and builds Modernizr
* `grunt assets` - Optimises image and script assets ready for release
* `grunt devupdates` - Only need to run at the start of a new project to check if dependencies need updating

## Additional scripts

The starter kit does include a couple of scripts and scaffolds that I consider useful and have found common need for on projects so delete as necessary. They are:

* [Headroom](https://github.com/WickyNilliams/headroom.js/) for the disappearing top header bar
* [Pushy](https://github.com/christophery/pushy) Off canvas navigation