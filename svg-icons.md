# SVG Icons

Here's a step-by-step guide to setting up a Gulp task to compile a set of SVG files into a single SVG file that you can embed in your page and use for your icons.

## 1. Install Gulp plugins

- Install [gulp-svgmin](https://www.npmjs.com/package/gulp-svgmin) and [gulp-svgstore](https://www.npmjs.com/package/gulp-svgstore)

```
$ npm install --save-dev gulp-svgmin
$ npm install --save-dev gulp-svgstore
```

## 2. Add task to your Gulpfile

Next, add an `icons` task to your `Gulpfile.js`:

```javascript
var gulp     = require( 'gulp' );
var svgmin   = require( 'gulp-svgmin' );
var svgstore = require( 'gulp-svgstore' );

// -------------------------------------
//   Options
// -------------------------------------

var options = {

  icons : {
    files       : 'source/images/icons/icon-*.svg',
    destination : 'source/images/icons'
  }

};

// -------------------------------------
//   Task: Icons
// -------------------------------------

gulp.task( 'icons', function() {

  gulp.src( options.icons.files )
    .pipe( svgmin() )
    .pipe( svgstore( { inlineSvg: true } ) )
    .pipe( gulp.dest( options.icons.destination ) );

});
```

## 3. Embed SVG file in page

```haml
.dn
  %img(src='assets/images/icons/icons.svg' alt='')
```

The `.dn` class is a utility class for `display: none`. We'll need this, since we want it to be hidden.

## 4. Reference the icon from the embedded file

To use an individual icon, you need to reference the one you want from the embedded SVG file:

```haml
%svg.icon{ width: 40, height: 40 }
  %use{ 'xlink:href' => '#icon-menu' }
```

To make things even easier, create an `_icon` partial file (if using Rails/Middleman, etc.):

```haml
- name   ||= ''
- size   ||= 40
- width  ||= size
- height ||= size

- unless defined? text
  %span.srt= name.humanize

%svg.icon{ width: width, height: height }
  %use{ 'xlink:href' => "#icon-#{ name }" }
```

Now you can call the partial, passing in appropriate options:

```haml
= render partial: 'icon', locals: { name: 'menu', size: 24 }
```
