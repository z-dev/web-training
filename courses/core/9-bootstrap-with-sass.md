#Bootstrap with Sass

# Outcome

You'll:

* Be able to import bootstrap via Sass.
* Be able to modify the default style of Bootstrap by overriding the bootstrap Sass variables.

# Prerequisites

* Sass, webpack

# Advice

The bootstrap css files you've been importing into your projects are actually generated using Less. There is a sister project to generate the css using Sass.

The Sass for the bootstrap project is split into various files. You can see the files [here](https://github.com/twbs/bootstrap-sass/tree/master/assets/stylesheets). Particularly the [main](https://github.com/twbs/bootstrap-sass/blob/master/assets/stylesheets/_bootstrap.scss) file and [variables](https://github.com/twbs/bootstrap-sass/blob/master/assets/stylesheets/bootstrap/_variables.scss) file.

Previously we've been overriding little bits of CSS here and there to change the style of bootstrap's default colors, font-sizes, fonts etc..

Now we can override some of those variables and control the exact theme of our site :smiley:

# Learning materials

# Core

* [Sass variables](https://github.com/twbs/bootstrap-sass/blob/master/assets/stylesheets/bootstrap/_variables.scss) Have a skim.
* [Less variables](http://getbootstrap.com/customize/#less-variables) In a nicer format than above, the names are the same / similar.

# Tasks

* *Skim* through the Sass/Less variables to get an idea of the kind of things you can modify (EVERYTHING!).
* Checkout the [sample webpack-bootstrap project](https://github.com/richardgill/webpack-bootstrap-seed).
  * Look at `main.scss`, `_bootstrap.scss` and `_variable_overrides.scss`.
  * In `_variable_overrides.scss` modify:
    * Default font
    * Primary brand color
* Convert Bear Medic to be Sass + Bootstrap :smiley:
