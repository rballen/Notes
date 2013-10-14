ruby and gems
======================================


### ruby via [rvm](http://rvm.io)

```sh
sudo apt-get curl
\curl -L https://get.rvm.io | bash -s stable --ignore-dotfiles
source ~/.rvm/scripts/rvm
rvm list known
rvm install 2.0.0 --autolibs=2; 
# install missing packages the run again...sudo apt-get xxx xxx
rvm install 2.0.0  --autolibs=2;
echo ". $HOME/.rvm/scripts/rvm" >> ~/.bashrc
echo "gem: --no-ri --no-rdoc" > ~/.gemrc   # don't isntall all the gems docs
. ~/.bashrc
rvm info   
```   

### [gems](http://rubygems.org/gems)

__develop, build, server, compass, sasss__    
```sh   
gem install bundler rake jekyll vagrant
gem install compass sass toolkit compass-recipes
gem install jsduck compass-colors color-schemer sassafras
gem install sassy-buttons animate-sass omg-text
gem install susy respondsass respond-to modular-scale
```

- [bundler](http://bundler.io/)
- [rake](http://rake.rubyforge.org/)
- [jekyll](http://jekyllrb.com/)
- [vagrant](http://www.vagrantup.com/)   
- [compass](http://compass-style.org/)
- [sass](http://sass-lang.com/)    
- [toolkit](https://github.com/Snugug/toolkit)
- [compass-recipes](http://compass-recipes.moox.fr/)
- [jsduck](https://github.com/senchalabs/jsduck)  
- [compass-colors](https://github.com/chriseppstein/compass-colors)
- [color-schemer](https://github.com/scottkellum/color-schemer)
- [sassafras](https://github.com/teejayvanslyke/sassafras)
- [sassy-buttons](http://jaredhardy.com/sassy-buttons/)
- [animate-sass](https://github.com/adamstac/animate.sass)
- [omg-text](http://jaredhardy.com/omg-text/)
- [respondsass](http://my-html-codes.com/respondsass/documentation.html)
- [respond-to](https://github.com/snugug/respond-to)
- [modular-scale](https://github.com/scottkellum/modular-scale)

___update___    
`gem update`                     # update installed rubies to latest version
`gem update --system`            # update rubygem software   
`gem update jekyll`              # update single gem
'gem install sass --pre'         # install upcoming sass release - source maps in chrome!!  
