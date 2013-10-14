[NodeJS](http://nodejs.org/) Setup & Resources 
=====================================
nodejs setup and package installs I use on new distros including raspberry-pi (debian version).
 
Setup
--------------------------------
**ubuntu / debian family**   
```sh
sudo apt-get install -y build-essential curl checkinstall make pkg-config git-core
sudo apt-get install -y openssl libxml2-dev libssl-dev gcc g++ apache2-utils
```
**arch distros**  
```sh
echo 'export PYTHON=python2' >> ~/.bash_profile
```

Nodejs Install 
--------------------------------
**ubuntu, raspberry-pi and  arch based distros**    
Read up on the latest stable version [here](http://nodejs.org/download/) or do a
`nvm ls-remote` to list them on the command line


```sh
wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh
```
I prefer .bashrc over bash_profile so open .profile or .bash_profile and remove the last line about nvm.sh


```sh
source ~/.nvm/nvm.sh
nvm ls   
nvm ls-remote   
nvm install v0.11.6
nvm alias default 0.11.6
echo '[[ -s "$HOME/.nvm/nvm.sh" ]] && . "$HOME/.nvm/nvm.sh" ' >> ~/.bashrc
echo '[[ -r "$HOME/.nvm/bash_completion" ]] && . "$HOME/.nvm/bash_completion" ' >> ~/.bashrc
ehco 'export node_path="$HOME/.nvm/v0.11.6/bin/node" ' >> ~/.bashrc
source ~/.bashrc   
node --version 

```

**raspberry-pi**  
`sudo pacman -S nodejs` and that's it for arch based pi's.

For debian based pi distros I do the following:

Since I don't want to use sudo and there's no nvm version, i install to /opt/node and change permsissions from root to myself. I feel like I have to justify my actions or the ghost of unix admins past will yell at me or something :)

Find latest stable arm-pi binary for debian based distros [here](http://nodejs.org/dist/)

```sh
sudo mkdir /opt/node
sudo chown -R ra:dev /opt/node
cd /opt/node
wget http://nodejs.org/dist/v0.11.3/node-v0.11.3-linux-arm-pi.tar.gz
tar xvzf node-v0.11.3-linux-arm-pi.tar.gz
rm node-v0.11.3-linux-arm-pi.tar.gz
mv node-v0.11.3-linux-arm-pi/* .
rm -rf node-v0.11.3-linux-arm-pi

echo 'NODE="/opt/node"' >> ~/.bashrc
echo 'export NODE_PATH="/opt/node/lib/node_modules"' >> ~/.bashrc
echo 'PATH="$PATH:$NODE/bin:$NODE/lib/node_modules”' >> ~/.bashrc
```
 
Packages
--------------------------------------
```sh
npm update -g npm            # update to latest npm
npm config set save true     # alwasy update package.json
npm install -g yo karma
npm install -g generator-webapp generator-angular generator-foundation
npm install -g http-server express generator-server-configs
npm install -g enhance-css caminte feedr
npm install -g coffee-script less jslint jslint 
npm install -g marked jsontool
npm install -g recess connect uglify-js hogan.js
npm install -g mongoose http-server
sudo npm install -g harp

cd ~/bin
wget https://phantomjs.googlecode.com/files/phantomjs-1.9.1-linux-x86_64.tar.bz2
tar xjf phantomjs-1.9.1-linux-x86_64.tar.bz2 phantomjs-1.9.1-linux-x86_64.tar.bz2
rm phantomjs-1.9.1-linux-x86_64.tar.bz2 phantomjs-1.9.1-linux-x86_64.tar.bz2
if [ -f ~/.profile ]; then echo 'PATH=~/bin/phantomjs-1.9.1-linux-x86_64/bin:$PATH' >> ~/.profile; fi
if [ -f ~/.bash_profile ]; then echo 'PATH=~/bin/phantomjs-1.9.1-linux-x86_64/bin:$PATH' >> ~/.bash_profile; fi
```


[npm](https://npmjs.org/) reference 
----------------------------------------
```bash
npm init										        # creates package.json
npm view hook.io
npm install <package>                       # local install of package (current directory) 
npm install -g <package>                    # global install    
npm install --save <package>                # install to project(local) and update package.json
npm install --save-dev <package>            # install to project and update devDependencies section in package.json
npm install git://github.com/package.git    # install from git repo
npm uninstall <package>                     # uninstall
npm config ls -l                            # list all config details for project
npm cache clean                             # clean up install packages' cache
npm update -g                               # update npm package
```

Discover
------------------------------------------
For ideas or discovery use search. Its like a %string% search on title and description field

```bash
npm search yeoman                      
npm search angular      
# bower was installed with 'yo' so you can also search bower - similiar yet different
bower search angular
```

For a good time visit also surf around on [npm website](https://npmjs.org/) - especially by tag


[cloud9 ide](https://github.com/ajaxorg/cloud9) 
------------------------------------------
this is at best dogy. the latest worked on [voyager 13.04](http://voyager.legtux.org/) (sans doute, la meilleure distro xubuntu/xfce)

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
  
put this code in an executable shell script named c9-projectname.sh on your path to launch anywhere. 
```sh
nvm use 0.8.22  
cd ~/bin/cloud9   
bin/cloud9.sh -p 4000 -w ~/Projects/webdev/    
google-chrome localhost:4000 
```


Resources
----------------------------------
- [docs](http://nodejs.org/api/)
- [nvm](https://github.com/creationix/nvm) - node verison management for multiple versions without using sudo 
- [npm](https://npmjs.org/) - node package manager
	- __packages__
	- [camintejs](http://www.camintejs.com/) ORM for mongodb, mysql, sqlite, neo4j    
	- [enhance-css](https://github.com/GoalSmashers/enhance-css) -base64 encoding, file minification and so much more
	- [yo](http://yeoman.io) - awesome yeoman fantastical thingy
	- [gruntjs](http://gruntjs.com/) - project management - its maven for nodejs/javascript projects
	- [bower](http://bower.io/) - awesome package management from the fine folks at twitter
- [nodetoolbox](http://nodetoolbox.com/) - listing of nodejs packages
- [phantomjs](http://phantomjs.org/)   
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
- [building a server out of javascript](http://weblog.bocoup.com/node-stress-test-serv)
- [debugging memory leaks](http://dtrace.org/blogs/bmc/2012/05/05/debugging-node-js-memory-leaks/)
