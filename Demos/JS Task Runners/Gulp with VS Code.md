# Gulp with VS Code
In this demo, we'll create a very simple font-end website that uses Gulp

### Pre Reqs
* [NodeJS and NPM installed](https://nodejs.org/en/)
* Visual Studio Code installed
* Have the snippets open in notepad or the VS code snippet files imported [see how(https://code.visualstudio.com/docs/editor/userdefinedsnippets) (the json files are in this repo)
* Gulp installed globally: `npm install -g gulp`

## Setup a project
Create a folder on the local disk

Right click > Open With Code

Create Index.html

Copy this basic code to the HTML doc (or use the `Lorum` extension in VS Code)
```
<h1>Sit minim ad ex qui consectetur adipisicing nisi reprehenderit quis Lorem et irure tempor laborum.</h1>
<p>Lorem do non ea mollit nulla adipisicing voluptate commodo deserunt. Eiusmod sit id eiusmod tempor qui esse commodo duis dolor in culpa sint. Occaecat aliqua deserunt fugiat proident magna consectetur nisi irure. Dolore non eiusmod nostrud magna elit. Pariatur ad anim pariatur velit anim reprehenderit culpa commodo esse. Sit labore magna incididunt Lorem est sunt fugiat commodo anim sit. Veniam dolore enim officia sit nisi dolor.</p>
<h2>Labore laboris ad veniam nostrud.</h2>
<p>Exercitation magna adipisicing cillum labore pariatur nisi aliquip ullamco veniam velit culpa. Adipisicing ea sint adipisicing ea aliquip minim velit minim ullamco sunt. Dolor eiusmod adipisicing incididunt magna. Elit ex mollit proident do fugiat duis tempor nulla ex aliqua veniam aliqua. Culpa minim mollit eu do aliquip.</p>
```

Create a folder called 'CSS'

Add a new file called Site.css

Copy this code into it
```
body {
    font-family: Arial;
    font-size: 14pt;
}
h1 {
    font-size:4rem;
    font-weight: bold;
    text-decoration: underline;
}
h2 {
    font-size:2rem;
    font-weight: bold;   
}
```

Show Index in a browser

## Install Gulp
Open a command at the same directory
* Right-click > Open in command prompt

Run `npm install gulp`

## Create a basic GulpFile
Add GulpFile.js to the project

Add this code
```
var gulp = require('gulp');
    
gulp.task('default', function () {
    console.log('Hello world');
});
```

In the command prompt run `gulp`
* Note the hello world message

## Add Gulp-minify-css
Open command at same directory as index.html
	
Run `NPM install gulp-minify-css`
	
Add var line to look like this
```
var minifycss = require("gulp-minify-css");
```

Add a task for CSS that pipes to wwwroot/css
```	
gulp.task("css_task", function () {
    gulp.src("css/*.css")
    .pipe(minifycss())
    .pipe(gulp.dest("wwwroot"));
});
```

Modify default task to include the css task
```
gulp.task('default', [ 'css_task' ]);
```
	
In command run `gulp`

Show the minified css file in wwwroot directory

Wire the new minified style sheet to the index by adding this line
```
<link href="./wwwroot/Site.css" rel="stylesheet">
```

Refresh browser to show style

## Add Autoprefixer
Look at hyphens in caniuse: http://caniuse.com/#search=hyphens

Add this to the css
```
p
{
    hyphens: auto;
}
```

Run `Npm install gulp-autoprefixer`
	
Add a var to the gulp file
```	
var autoprefixer = require('gulp-autoprefixer');
```

Add this line beneath `gulp.src("css/*.css")` in the css_task
```
.pipe(autoprefixer())
```

In command run 'gulp'

Show that the css file in wwwroot now includes the various required vendor prefixes

Show that the site now has hyphenated P tags

## Add a watch
Add this watch task to gulpfile.js
```
gulp.task('csswatch_task', function() {
	gulp.watch('css/*.css', ['css_task']);
});
```

Update the default task to include the watch
```
gulp.task('default', ['css_task', 'csswatch_task']);
```

In command run 'gulp'

Modify the css by adding this css
```
h1
{
    color: red;
}
```

Show the updated minified css in wwwroot

Show the updated Index page
