# Automating WordPress Theme Tasks using Gulp
My workflow involves using Gulp to automate certain tasks on almost all theme builds I carry out. This includes:

* Installing bower components.
* Compiling SCSS.
* Optimizing images.
* Creating language .pot files.
* Concatenating and linting JavaScript.
* Adding BrowserSync support allowing instant reload in web browser.

Until now I have just included these tasks within my starter theme, however it would make more sense to separate these tasks into their own repository so they can be worked on and improved from one central location, without having to then update multiple theme builds.

## Installation
Clone this repo to your theme folder, then run `npm install`. Configure the settings within `/tasks/config.js` to suit the project (there are source paths, destination paths, notification messages for each task defined there).

## Running Tasks
The following tasks are available:

* `gulp` is a default watch tasks. Changes within source directories will result in the appropriate task being run and files output in destination directory.
* `gulp serve` is a default watch task, but initializes BrowserSync with the proxy URL entered in `config.js`.
* `gulp build` runs all tasks (typically would be used on first install to get everything from `/assets/` to the theme root.
* `gulp bower` will check for a bower.json in the theme root (one level up) and run `bower install`.
* `gulp scripts` concatenates all scripts from `/assets/js/` to a single file (default `theme.js`) in a `/js/` folder in the theme root.
* `gulp images` optimizes and outputs all images from '/assets/images/' to `/images/` within the theme.
* `gulp styles` compiles SCSS in `/assets/scss/` to `style.css` and `style.css.map`.
