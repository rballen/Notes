ruby and gems
======================================


### ruby via [rvm](http://rvm.io)
```sh
\curl -L https://get.rvm.io | bash -s stable
echo 'source ~/.rvm/scripts/rvm' >> ~/.bashrc
source ~/.bashrc
rvm requirements  # install any requirements
```
verify that output of:   
`type rvm | head -n 1`
should be `rvm is a function`  
```sh
rvm list known          # list known rubies
rvm install 2.0.0-p195  # install 2.0
rvm use 2.0.0-p195 --default     # use it and set it to default
ruby -v 				# verify version
which ruby				# verify location
rvm info                # all the details
```   
to make things faster i don't install the docs and set it globally in my ~/.gemrc   
`gem: --no-ri --no-rdoc`   

### [gems](http://rubygems.org/gems)

__develop, build, serve__   
`gem install --no-rdoc --no-ri bundler rake jekyll vagrant`[bundler](http://bundler.io/), [rake](http://rake.rubyforge.org/),  [jekyll](http://jekyllrb.com/), [vagrant](http://www.vagrantup.com/)   

__modern webdev__    
`gem install compass sass`  [compass](http://compass-style.org/) ,[sass](http://sass-lang.com/)    

__sass & compass helpers__   
`gem install --no-rdoc --no-ri toolkit compass-recipes compass-normalize` [toolkit](https://github.com/Snugug/toolkit) , [compass-recipes](http://compass-recipes.moox.fr/)

__document__   
`gem install --no-rdoc --no-ri jsduck`    [jsduck](https://github.com/senchalabs/jsduck)    

___sassy color help___    
`gem install compass-colors color-schemer sassafras` [compass-colors](https://github.com/chriseppstein/compass-colors) , [color-schemer](https://github.com/scottkellum/color-schemer), [sassafras](https://github.com/teejayvanslyke/sassafras)
  
___frameworks___     
`gem install --no-rdoc --no-ri bootstrap-sass zurb-foundation` [bootstrap-sass](https://github.com/thomas-mcdonald/bootstrap-sass), [zurb-foundation](http://foundation.zurb.com/docs/sass.html), [bourbon](http://bourbon.io/), [neat](http://neat.bourbon.io/)  

___ui___    
`gem install --no-rdoc --no-ri sassy-buttons animate-sass omg-text` [sassy-buttons](http://jaredhardy.com/sassy-buttons/), [animate-sass](https://github.com/adamstac/animate.sass), [omg-text](http://jaredhardy.com/omg-text/)

___responsive___   
`gem install --no-rdoc --no-ri susy respondsass respond-to modular-scale` [respondsass](http://my-html-codes.com/respondsass/documentation.html), [respond-to](https://github.com/snugug/respond-to), [modular-scale](https://github.com/scottkellum/modular-scale)

___update___    
`gem update`                     # update installed rubies to latest version
`gem update --system`            # update rubygem software   
`gem update zurb-foundation`     # update single gem
