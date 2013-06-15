[NodeJS](http://nodejs.org/) Setup & Resources 
=================================
Aggregating my nodejs resources - quick setup, tutorials, cloud9 ide. useful packages...

### Resources
- [docs](http://nodejs.org/api/)
- [npm](https://npmjs.org/) - node package manager
- [nodetoolbox](http://nodetoolbox.com/) - listing of nodejs packages
- [nodeup](http://nodeup.com/) - nodejs podcast
- [nodejitsu](http://docs.nodejitsu.com/)
   - [package.json cheatsheet](http://package.json.nodejitsu.com/)
   - [npm cheatsheet](http://blog.nodejitsu.com/npm-cheatsheet)
- [howtonode](http://howtonode.org)
- [Felix nodejs guide](http://nodeguide.com/)
- [Cloud9 and node examples](https://github.com/c9/nodemanual.org-examples)
- [nodemanual](https://github.com/c9/nodemanual.org) - essential Node.js dags, API references, and developer tutorials.
- [nodejs@stackoverflow.com](http://stackoverflow.com/questions/tagged/node.js)
- [planet nodejs](http://planetnodejs.com/)
- [nodejs hosting roundup](http://saewitz.com/node-dot-js-websocket-hosting-roundup/)
- [building a server](http://weblog.bocoup.com/node-stress-test-serv)
- [debugging mem leeks](http://dtrace.org/blogs/bmc/2012/05/05/debugging-node-js-memory-leaks/)

### debian based dependancies
```ag
sudo apt-get install -y build-essential curl checkinstall make pkg-config git-core   
sudo apt-get install -y openssl libxml2-dev libssl-dev gcc g++ apache2-utils   
```

### Installation with [nvm](https://raw.github.com/creationix/nvm)
arch linux add `export PYTHON=python2` to your .bash_profile    
```sh  
wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh  
# open ~/.bash_profile or ~/.profile and cut the last line about nvm.sh and paste to end of your ~/.bashrc
source ~/.bashrc
nvm ls-remote   # list nodejs versions   
nvm ls          # list local versions    
nvm install v0.10.2   # use latest as default
nvm alias default 0.10.2   # sets the default version
node --version     
echo '[[ -r $NVM_DIR/bash_completion ]] && . $NVM_DIR/bash_completion' >> .bashrc
source ~/.bashrc
nvm [tab][tab]
```
### [npm](https://npmjs.org/) - Node Package Manager
npm <command> : install update search author docs list linkj tag uninstall update etc   
```sh
npm update npm -g   
npm install <package>       # local install   
npm install -g <package>    # global install   
```
### Packages
[__angularjs__](http://angularjs.org/)    
`npm install -g angular karma`        

[__yeoman__](http://yeoman.io)   
`npm install -g yo grunt-cli bower`    # yeoman,  grunt and bower     
`npm install -g yeoman-foundation`     # scafolding for zurb foundation  
`npm install -g generator-angular`     # scafolding for angularjs 

[__docpad__](http://docpad.org/docs/plugins)    
`npm install -g npm`     # update npm first   
`npm install -g docpad@6.29`   

__popular__   
```sh
npm install -g enhance-css     # base64 all images in css   
npm install -g caminte  # ORM: mongodb, mysql, sqlite, neo4j  http://www.camintejs.com/   
npm install --save feedr   # convert all feeds to json    
npm install -g node-dev node-inspector nodemon
npm install -g express coffee-script jslint less   
npm install -g marked jsontool   
npm install -g recess connect uglify-js jshint hogan.js
```
### related
- [phantomjs](http://phantomjs.org/)
- [couchdb with nodejs](http://zoddy.github.com/cushion/)    

### couchdb
sudo apt-get install couchdb
git clone https://github.com/Zoddy/cushion.git

### mongodb
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10
echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/10gen.list
sudo apt-get update && sudo apt-get install mongodb-10gen
sudo service mongodb start
gem install humongous
humongous  # at cli to start 
humongous -K # at cli to stop
install robomongo from http://robomongo.org/

### [cloud9 ide](https://github.com/ajaxorg/cloud9) 
this worked on ubuntu 13.04 and manjaro (arch) 8.5.1     
__install__   
```sh
nvm install v0.8.22  
nvm use 0.8.22   
cd ~/bin   
git clone https://github.com/ajaxorg/cloud9.git 
cd cloud9
npm install
```
__update__   
```sh   
git pull       
npm update     
npm install      
```
__code__   
put this code in an executable shell script named c9-projectname.sh on your path to launch anywhere. 
```sh
nvm use 0.8.22  
cd ~/bin/cloud9   
bin/cloud9.sh -p 4000 -w ~/Projects/foundation/    
google-chrome localhost:4000 
```
