ruby and gems
======================================

### Install with [rvm](http://rvm.io)
```sh
\curl -L https://get.rvm.io | bash -s stable --ruby
echo 'source ~/.rvm/scripts/rvm' >> ~/.bashrc
source ~/.bashrc
rvm requirements 
```
verify that output of:   
`type rvm | head -n 1`
should be `rvm is a function`  
```sh
rvm list known
rvm requirements        # for any dependancies
rvm info                # all the details
```

#### userful gems for webdev
`gem install bundler rake jekyll`          
[toolkit](https://github.com/Snugug/toolkit) - `gem install jsduck toolkit`    
___color___    
`gem install compass compass-recipes compass-colors`      
[color-schemer](https://github.com/scottkellum/color-schemer) - `gem install color-schemer`    
___frameworks___    
`gem install bootstrap-sass zurb-foundation`   
___ui___   
`gem install sassy-buttons`   
`gem install animate-sass`      http://daneden.me/animate/     
`gem install omg-text`          https://github.com/jhardy/OMG-TEXT   
___responsive___   
`gem install susy`  
`gem install respondsass`       http://my-html-codes.com/respondsass/documentation.html        
`gem install respond-to`        https://github.com/snugug/respond-to   
`gem install modular-scale`     https://github.com/scottkellum/modular-scale;   
`gem install bourbon neat`     http://bourbon.io/docs   
___update___   
`gem update --system`           # update gems to latest   
`gem update zurb-foundation`     # update single gem
