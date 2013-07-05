[Compass](http://compass-style.org/) and [SASS](http://sass-lang.com) Reference
========================================
| compass   | sass          |  resources         |
| --------- |:------------- | -------------:| 
|[compass](http://compass-style.org/reference/compass/)|[Compass Recipes](http://compass-recipes.moox.fr/) |[35 Resources for Compass and Sass](http://fuelyourcoding.com/35-great-resources-for-compass-and-sass/)|
|[sass](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html)|[sass/less cheat sheet](https://gist.github.com/chriseppstein/674726)|[sassmeister](http://sassmeister.com/)|

 
### Install
depends on ruby and some gems outlined in [ruby-gem-reference](https://github.com/rballen/documents/blob/master/ruby-gem-reference.md)

__xtra steps for my dreamhost shared:__
```sh
rvm pkg install libyaml && rvm reinstall all --force
gem install compass
gem install sass
```
### Usage
```sh
compass help          (show all commands)  
compass frameworks    (list frameworks)
compass validate      (compile css and validate with W3C)
compass compile      (compile to css)
compass watch      (watch for changes and compile)
sass sass/main.scss:stylesheets/main.css  (compile sass)
sass --watch sass/dir:css/dir    (watch for changes and compile)
```
### Projects
[__Zurb Foundation__](http://foundation.zurb.com/docs/sass.html)   
```sh
gem install zurb-foundation
gem update zurb-foundation
compass create my_project -r zurb-foundation --using foundation
```
- override sass/settings.scss to customize
- [templates](http://foundation.zurb.com/templates.php)

[__bootstrap-sass__](https://github.com/thomas-mcdonald/bootstrap-sass)      
```sh
gem install bootstrap-sass 
compass create my_project -r bootstrap-sass --using bootstrap
# add require bootstrap-sass to config.rb  
# existing projects use: compass install bootstrap  
# add @import "bootstrap"; to end of your scss file   
# in your main.sass file, make your custom changes first then import boostrap to overide   
@import "bootstrap";
@import "bootstrap-responsive";   
```       
__[singularity](https://github.com/Team-Sass/Singularity/wiki)__    
[video walkthru](http://vimeo.com/63509346)   
```sh
gem install singularitygs
compass create {project name} -r singularitygs --using singularitygs
gem install singularity-extras
```
add require 'singularitygs' to existing proeject    
if you want to use [grid-toggle](https://github.com/Team-Sass/Singularity/wiki/Creating-Grids#visualizing-your-grids) the grid visualizer you need [grid.js](https://github.com/Team-Sass/Singularity/blob/1.x.x/templates/project/grid.js)

for ie 6 ad 7 you'll need this polyfil `compass install singularitygs/box-sizing`

singularity demo can be seen with `compass create sgs-demos -r singularitygs --using singularitygs/demos`

[Susy responsive grids](http://susy.oddbird.net/) - `gem install susy`
> [grid-types](http://susy.oddbird.net/demos/grid-types/)

[RespondSASS](http://my-html-codes.com/respondsass/index.html) - `gem install respondsass`
> `compass create my_project -r respondsass --using respondsass`

- [sassy buttons](http://jaredhardy.com/sassy-buttons/) -`gem install sassy-buttons` | config.rg: `require 'sassy-buttons'`  
> `@include sassy-button(gradient-style, border-radius, font-size, first-color, second-color, text-color, text-style, auto-states)`  
> `@include sassy-button("shiny", 15px, 26px, #ffd71a, #ffaa1a);`  

- [fancy-buttons](xxx) - `gem install fancy-buttons`

- [Zocial CSS3 Social Buttons](http://zocial.smcllns.com/sample.html) - add a class "zocial" and a class for the brand. wrap your button text in a span. 
> acrobat,  bitcoin,  cloudapp,  dropbox,  email,  eventful, github, gmail, instapaper, itunes, ninetyninedesigns, openid, plancast, pocket, posterous, reddit, secondary, sackoverflow, viadeo, weibo, wikipedia  
>`<button class="zocial facebook">Sign in with Facebook</button>`  
`<a class="zocial linkedin">Sign in with LinkedIn</a>`  
`<button class="zocial skype" style="font-size: 22px">Skype Me</button>`  
`<a class="zocial twitter icon">Follow me on Twitter</a>`  

- [animate-sass](http://daneden.me/animate/) -`gem install animate-sass`  | config.rb:`require 'animate-sass'` | `@import "animate.sass"`

- [Color functions](http://robots.thoughtbot.com/post/12974565313/controlling-color-with-sass-color-functions)

- [omg-text](http://jaredhardy.com/omg-text/) - gem install omg-text

- [compass-recipes](http://compass-recipes.moox.fr/) - `gem install compass-recipes`  |   config.rb:`require 'compass-recipe`
    > `@import "recipes/shape/triangle";`

- [bourbon](http://bourbon.io/docs/) - `gem install bourbon`

- [neat](http://neat.bourbon.io) - `gem install neat`
          
- [toolkit](https://github.com/Snugug/toolkit) - `gem install toolkit`

- [color-schemer]( https://github.com/scottkellum/color-schemer) - `gem install color-schemer`

- [modular-scale](https://github.com/scottkellum/modular-scale) - `gem install modular-scale`

- [respond-to ]( https://github.com/snugug/respond-to) - `gem install respond-to `



### Snippets

___no prefixes___
.selector {
  @include box-shadow(#{0 2px 5px rgba(0,0,0,.25) inset, 0 -2px 5px rgba(0,0,0,.25) inset});
}

___responsive___
```
.profile-pic {
  float: left;
  width: 250px;
}
@media only screen and (max-width: 320px) {
  .profile-pic {
    width: 100%;
  }
}
@media only screen and (min-width: 321px) and (max-width: 1023px) {
  .profile-pic {
    width: 125px;
  }
}
@media only screen and (min-width: 1024px) {
  .profile-pic {
    float: none;
  }
}
```
___variables___
```
$darkgrey: #333333;
$lightblue: #001eff;
$lightred: #ff0000; // set your new color…
 
$text_color: $darkgrey;
$link_color: $lightred; // …and use it here
$border_color: $lightblue;
```
___nesting___
```
.myClass{
  color: $text_color;
  border-color: $border_color;
}
a{
  color: $link_color;
}
```
