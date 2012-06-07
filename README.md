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
  @mixin border-radius($amount) {
    -webkit-border-radius: $amount !important;
    -moz-border-radius   : $amount !important;
    -ms-border-radius    : $amount !important;
    -o-border-radius     : $amount !important;
    border-radius        : $amount !important;
  }
  @mixin box-shadow($arg) {
    -webkit-box-shadow: $arg;
    -moz-box-shadow   : $arg;
    box-shadow        : $arg;
  }
  @mixin opacity($amount) {
    -khtml-opacity: $amount;
    -moz-opacity  : $amount;
    opacity       : $amount;
    filter        : progid:DXImageTransform.Microsoft.Alpha(opacity=(#{$amount * 100}));
  }
  @mixin transform($args) {
    -webkit-transform: $args;
    -moz-transform   : $args;
    -ms-transform    : $args;
    -o-transform     : $args;
    transform        : $args;
  }
  @mixin delay($count) {
    -webkit-transition-delay: #{$count}s;
    -moz-transition-delay: #{$count}s;
    // -ms-transition-delay: #{$count}s; -----Not available in IE...yet. -rwp
    -o-transition-delay: #{$count}s;
    transition-delay: #{$count}s;
  }
  @mixin transition($arg) {
    -webkit-transition: $arg;
    -moz-transition: $arg;
    -o-transition: $arg;
    transition: $arg;
  }
```

## The Variables (an ever-growing list)
```scss
  $white                 : #FFFFFF;
  $whitesmoke            : #F5F5F5;
  $gray                  : #CCCCCC;
  $ive-got-a-crush-on-you: #FEE4B8;
  $blue-mimozaa          : #28FFCD;
  $seabreeze             : #55989B;
  $limealicious          : #A9FD39;
  $power-c               : #790D85;
```

## Getting started with the example
    (Required: RubyGems, Git, Ruby >= v1.9.2)
    $ git clone git@github.com:rpearce/bertstrap.git
    $ cd example
    $ gem install bundler
    $ bundle
    $ ruby app.rb
    Navigate to http://localhost:4567

## Compile SCSS files to CSS folder:
    $ sass --watch public/stylesheets/scss/:public/stylesheets/css
