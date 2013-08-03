[Yeoman](http://yeoman.io/commandline.html)
===========================
Modern workflows for modern webapps
>creates project structure, minifies, concatenates, optimizes images, compiles coffee-script and compass, lints, built in server, packages, builds, deploys, tests, my goodness.

### Install
___requires node.js___   
`npm install -g yo `  - installs grunt-cli and bower automatically          
`npm install -g generator-angular` - basic angular scafolding     
`npm install -g generator-webapp`  - basic vanilla webapp scafolding   
> name : [ember, angular, bootstrap, backbone, bbb, chrome-extension, foundation, jasmine, karma, mocha, jquery, chromeapp]

### Basic webapp 
`yo <generator> [arguments] [--help]`   

```sh
yo webapp my-app                    # scaffold out a skeleton web app project
npm install && bower install   # install default dependencies
bower install underscore       # install a dependency for your project from Bower
grunt                          # build the application for deployment
```
### [AngularJS](http://angularjs.org/)
`yo angular` for basic scaffolding   
`yo angular:<command>` : route, controller, directive, filter, view   

- `yo angular:route` 
    - Generates a view and controller, wires them in app/scripts/app.js
- `yo angular:controller user`
- `yo angular:directive myDirective`
- `yo angular:filter myFilter`
- `yo angular:view user`
- `yo angular:service myService`
    - __service options:__  
    - --factory (default) 
    - --service
    - --value
    - --constant

__[anular-ui](http://angular-ui.github.com/)__ and [karma tests](http://karma-runner.github.com/0.8/index.html)
```sh
mkdir my-app && cd $_
npm install generator-angular generator-karma 
yo angular [my-app]           # scaffold AngularJS project with optional name [appname]
npm install && bower install --dev   # install default dependencies
bower install angular-ui       # install a dependency for your project from Bower
grunt test                     # test your app
grunt server                   # preview your app
grunt                          # build the application for deployment
```

### [Bower](http://twitter.github.com/bower/) - package manager from twitter
```sh
bower search  {dep}         # search for a dependency in  registry:  bower search jquery-bbq
bower install {dep}..{dep} # install one or more dependencies
bower list                  # list out the dependencies you have installed for a project
bower update {dep}          # update a dependency to the latest version available
```
####[Bower Components](http://sindresorhus.com/bower-components/)  
`bower update`  for latest components    
`bower install angular-ui angular-cookies angular-loader angular-resource angular-sanitize angular-mocks`      

### [Grunt](http://gruntjs.com/) -  build tool for JavaScript projects.
```sh
grunt         # builds an optimized, production-ready version of your app
grunt server  # preview an app you have generated (with Livereload)
grunt test    # run the unit tests for an app
```
