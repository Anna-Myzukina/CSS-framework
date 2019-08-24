# CSS-framework
PROJECT: DESIGN YOUR OWN GRID-BASED FRAMEWORK
- [Preview](https://anna-myzukina.github.io/CSS-framework/)

## Useful links:
- [Simple grid mixins](http://thesassway.com/intermediate/simple-grid-mixins)
- [Generate All Your Utility Classes with Sass Maps](https://frontstuff.io/generate-all-your-utility-classes-with-sass-maps)
- [GitHub Readme Images Tutorial (screenshots in readmes)](https://www.google.com/search?q=add+screenshots+to+github+readme&oq=add+scre&aqs=chrome.0.69i59j69i57j0l4.2782j0j7&sourceid=chrome&ie=UTF-8)
## This formula create next properties for margin/padding : 
* $sides:(top, bottom, left, right);
* $sizes:(sm, md, lg);
* $values:1rem;

@each $side in $sides {
  @each $value in $values {
    @each $size in $sizes {
      .margin-#{$side}-#{$size}-#{$value} {
        @if $size==sm {
          $new_val: round($value/4);
          margin-#{$side}:#{$new_val}rem;
        }

        @else if $size==md {
          $new_val: round($value/3);
          margin-#{$side}:#{$new_val}px;
        }

        @else if $size==lg {
          $new_val: round($value);
          margin-#{$side}:#{$new_val}px;
        }
      }

      .padding-#{$side}-#{$size}-#{$value} {
        @if $size==sm {
          $new_val: round($value/4);
          padding-#{$side}:#{$new_val}px;
        }

        @else if $size==md {
          $new_val: round($value/3);
          padding-#{$side}:#{$new_val}px;
        }

        @else if $size==lg {
          $new_val: round($value);
          padding-#{$side}:#{$new_val}px;
        }
      }
      .padding-#{$side}-#{$size}-#{$value} {
        @if $size==sm {
          $new_val: round($value/4);
          padding-#{$side}:#{$new_val}px;
        }

        @else if $size==md {
          $new_val: round($value/3);
          padding-#{$side}:#{$new_val}px;
        }

        @else if $size==lg {
          $new_val: round($value);
          padding-#{$side}:#{$new_val}px;
        }
      }
    }
  }
}



##  keys with properties of sizes of screen this arrey we use in next part to create madia
      $breakpoints: ('small': 425px,
          'medium': 768px,
          'large': 1024px,
          'huge': 1200px);

/// this variable means number of column in your project, if you need you can
///  change to any number and use next formula to create grid system:
        $cols: 12;

        @mixin break($size) {
            @media (min-width: map-get($breakpoints, $size)) {  //syntaxis : map-get($map, $key)function 
                //the function returns the value in the map associated with the given key
                @content;
            }
        }

        @each $key,$value in $breakpoints { //the each rule evaluates a block of styles for each key/value pair in map
            @include break($key) {
                @for $i from 1 through $cols {
                    .col-#{$key}-#{$i} {
                        width: #{$i / $cols * 100%};
                        float: left;
                    }
                }

            }
        }

        /// author Nicolas Gallanger
        /// link http://nicolasgallagher.com/micro-clearfix-hack/ Micro Clearfix

        @mixin clearfix() {
            &:after {
                content: "";
                display: block;
                clear: both;
            }

            &:before {
                content: "";
                display: block;
                clear: both;
            }

        }

        .row {
            @include clearfix;
        }
        
        
        
        
        x-special/nautilus-clipboard


![github-small](assets/img/Screenshot%20from%202019-08-23%2014-13-48.png)


