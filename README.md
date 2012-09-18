# bertstrap
Library for generic SCSS mixins and colour variables.

## Using SCSS/SASS partials
Given you have an SCSS file with your specific stylings for elements,
you can import "partial" files which are not compiled to a CSS file of
their own. So when you "import" that file, the actual file that you want
compiled will compile normally, including all the mixin and variable
values which you included in separate files.

Note        : Partials are denoted by an underscore (_) before the file name.
Example file: _core_mixins.scss

In your main file, you simply import the file via:
```scss
  @import '_core_mixins';
```

And then you have access to all the mixins from that file! Yay!

## The Mixins
```scss
$box-shadow-prefixes: -webkit-box-shadow, -moz-box-shadow, box-shadow; // a list required for mixin #2

@mixin border-radius($amount) {
  -webkit-border-radius: $amount;
     -moz-border-radius: $amount;
      -ms-border-radius: $amount;
       -o-border-radius: $amount;
          border-radius: $amount;
}

@mixin box-shadow($arg, $arg2: null, $arg3: null) {
  $arguments: $arg, $arg2, $arg3;
  @each $property in $box-shadow-prefixes {
    #{$property}: $arguments;
  }
}

@mixin opacity($amount) {
  -khtml-opacity: $amount;
    -moz-opacity: $amount;
         opacity: $amount;
          filter: progid:DXImageTransform.Microsoft.Alpha(opacity=(#{$amount * 100}));
}

@mixin transform($args) {
  -webkit-transform: $args;
     -moz-transform: $args;
      -ms-transform: $args;
       -o-transform: $args;
          transform: $args;
}

@mixin transition($arg) {
  -webkit-transition: $arg;
     -moz-transition: $arg;
       -o-transition: $arg;
          transition: $arg;
}

// Shorthand for transition delay time amount in seconds
@mixin delay($count) {
  -webkit-transition-delay: #{$count}s;
     -moz-transition-delay: #{$count}s;
       -o-transition-delay: #{$count}s;
          transition-delay: #{$count}s;
}
```

## The Variables (an ever-growing list)
```scss
  $white                 : #FFF;
  $whitesmoke            : #F5F5F5;
  $gray                  : #CCC;
  $ive-got-a-crush-on-you: #FEE4B8;
  $blue-mimozaa          : #28FFCD;
  $seabreeze             : #55989B;
  $limealicious          : #A9FD39;
  $power-c               : #790D85;
```

## Getting started with the example
    (Required: RubyGems, Git, Ruby >= v1.9.2)
    $ git clone git@github.com:rpearce/bertstrap.git
    $ gem install bundler
    $ bundle
    $ ruby app.rb
    Navigate to http://localhost:4567

## Compile SCSS files to CSS folder in compressed form:
    $ sass --watch ./public/stylesheets/scss/:./public/stylesheets/css --style compressed
