#### [Yeoman - Modern workflows for modern webapps](http://yeoman.io/commandline.html  "Modern workflows for modern webapps")

#### Commands & Topics

*   `yeoman --help` or `yeoman help`
*   `yeoman init --help`

    yeoman init      # Initialize and scaffold a new project using generator templates
    yeoman build     # Build an optimized version of your app, ready to deploy
    yeoman server    # Launch a preview server which will begin watching for changes
    yeoman test      # Run a Mocha test harness in a headless PhantomJS
    
    yeoman install   # Install a package from the clientside package registry
    yeoman uninstall # Uninstall the package
    yeoman update    # Update a package to the latest version
    yeoman list      # List the packages currently installed
    yeoman search    # Query the registry for matching package names
    yeoman lookup    # Look up info on a particular package
    
The default `init` template is based on:

*   HTML5 Boilerplate for the main base
*   Compass Twitter Bootstrap for the SASS files as the CSS files are authored in SASS
*   Twitter Bootstrap for the optional list of JavaScript plugins (optional)
*   RequireJS for AMD module and script loading support (optional)
*   RequireHM for experimental EcmaScript 6 module syntax support on top of RequireJS (optional)
* supports Compass and CoffeeScript by default, so auto compiled with `server` or `build` tasks

#### Generators & Sub Generators
    yeoman init
    yeoman init *generatorName*
    yeoman init *generatorName:subgenerator*

    yeoman init bbb      # backbone boilerplate
    yeoman init angular  # angularjs seed
    yeoman init ember    # ember app based on ember-rails

    Angular:
      angular:all
      angular:app
      angular:common
      angular:controller
      angular:directive
      angular:filter
      angular:route
      angular:service
      angular:view

    Backbone:
      backbone:all
      backbone:app
      backbone:collection
      backbone:model
      backbone:router
      backbone:view

    Bbb:
      bbb:all

    Chromeapp:
      chromeapp:all

    Ember-starter:
      ember-starter:all

    Ember:
      ember:all
      ember:app
      ember:controller
      ember:model
      ember:view

    Mocha:
      mocha:generator

    Quickstart:
      quickstart:all

    Testacular:
      testacular:app

      
**angular**

     yeoman init angular - same as calling  `angular:all` 
     yeoman init angular:controller controllerName - controllerName is the name of the Controller you wish to create.

**backbone**

     yeoman init backbone -  boilerplate for models, views, collections and a router as well as Backbone.js and its dependencies
     yeoman init backbone:model modelName
     yeoman init backbone:collection collectionName
     yeoman init backbone:view viewName
     yeoman init backbone:router routerName
    

#### Building   

Usage: `yeoman build`, `yeoman build:` - builds optimized version of app, ready to deploy.

Uses [Grunt][1] 

*   Linting all JavaScript files against JSHint
*   Recompiling all CoffeeScript and SASS files for production
*   Using r.js to compile and optimize any AMD modules
*   Concatenation and minification of scripts and stylesheets
*   Compressing your images using OptiPNG for PNG files and JPEGtran-turbo for JPEGs
*   Running any unit tests written against a headless WebKit browser (via PhantomJS)
*   Creating an Application Cache manifest via Confess.js
*   Using revision filenames or oldernames

Create 'Gruntfile.js' with build configuration and any customization. Customized to support which paths to watch, have compiled (Compass, CoffeeScript, etc).

`yeoman server` generates temporary temp dir `temp`, with compiled version to  preview app.

`yeoman build` creates a `dist` directory which has completely optimized version of your application that can be deployed to staging.

#### Build targets

*   `yeoman build` Runs `concat css min img rev usemin manifest`
*   `yeoman build:text` `concat css min rev usemin manifest`
*   `yeoman build:buildkit` Runs `concat css min img rev usemin manifest html:buildkit`
*   `yeoman build:basics` Runs `concat css min img rev usemin manifest html:basics`
*   `yeoman build:minify` Runs `concat css min img rev usemin manifest html:compress`

#### Sub-tasks

Each build target above runs a number of different build *tasks*. The supported tasks included with Yeoman out of the box are:

*   clean: Wipe the previous build dirs
*   copy: Copies the whole staging(intermediate/) folder to output (publish/) one
*   css: Concatenates, replaces @imports and minifies the CSS files
*   dom: DOM-based build system
*   html: Basic to aggressive HTML minification
*   img: Optimizes .png/.jpg images using OptiPNG/JPEGtran
*   mkdirs: Prepares the build dirs
*   rev: Automate the hash renames of assets filename
*   usemin: Replaces references to non-minified scripts / stylesheets

#### Require.js / r.js configuration

Yeoman has a special task that automatically handles the optimization of Require.js/AMD projects using the r.js optimizer. Configuration for this optimization (i.e your r.js configuration) should be done within the `rjs` section of the Gruntfile for a project.

You can either do this at a project level by editing your projects Gruntfile or do this at a generator level if you would rather avoid editing the Gruntfile outside of the default setup each time.

The following is the relevant block to edit within your Gruntfile:

    // rjs configuration. You don't necessarily need to specify the typical
    // `path` configuration, the rjs task will parse these values from your
    // main module, using http://requirejs.org/docs/optimization.html#mainConfigFile
    //
    // name / out / mainConfig file should be used. You can let it blank if
    // you're using usemin-handler to parse rjs config from markup (default
    // setup)
    rjs: {
      // no minification, is done by the min task
      optimize: 'none',
      baseUrl: './scripts',
      wrap: true
    }
    

#### Server
`yeoman server` - [localhost:3501](http://localhost:3501)

It also automatically fires up the `yeoman watch` process, so changes to any of the applications files cause the browser to refresh via [LiveReload][3]. Should you not have LiveReload installed locally, a fallback reload process will be used instead.

Any changes to CoffeeScript or Compass files result in them being recompiled, meaning that no manual intervention is required to write and preview code in the format you feel most comfortable with.

`yeoman server` generates an intermediate build directory in your project root which (called `temp`) contains the compiled files mentioned above as well as the basic blocks needed to preview your application. A complete build can be generated using `yeoman build`.

To quit the server, simply use `ctrl%2Bc` and this will kill the Yeoman server process.

### profiles

The built-in server also supports serving different profiles of your application, such as: `app`, `dist`, `test` and `reload`.

*   `yeoman server` and `server:app` compile to and serve `/temp`, an intermediate build of your application.
*   `yeoman server:dist` serves up the optimized final version of your application. This will just serve up the `/dist` directory if it exists and you will need to run `yeoman build` in order to generate the production build of your app.
*   `yeoman server:test` serves up the test suite and your `app`. It also ensure any change to your code or tests will cause the browser to refresh.
*   `yeoman server:reload` forces the port to be LiveReload standard port: 35729 and prevents the automatic default browser opening. Handy for those wishing to use livereload extensions with other systems / HTTP servers than the one provided by Yeoman out of the box.

#### test

Runs a Mocha test harness in a headless instance of PhantomJS.

When you generate a new project using `yeoman init`, we also scaffold out a basic set of Mocha unit tests that you can continue using to test your application.

Running `yeoman test` allows you to easily check if all of your tests are passing. This also gets called when running `yeoman build`.

A dedicated server, with visibility on `app`, `temp` and `test` is launched to serve file for PhantomJS.

Example:

    yeoman test
    
    # outputs:
    
    Running "mocha:all" (mocha) task
    Running specs for index.html
    .....................................................
    &gt;&gt; 82 assertions passed in 53 specs (562ms)
    
    Done, without errors.
    

Usage: `yeoman install `, `yeoman install  `

Installs a package and any packages that this depends on using Twitter Bower. A package is a folder containing a resource described by a package.json file or a gzipped tarball containing this information.

By default, running `yeoman install packageName` will install the dependency in your projects `app/components` folder.

Example:

    yeoman install backbone
    
    # or if you wish to install multiple packages at once..
    yeoman install jquery spine
    

As mentioned, the files for these dependencies will be added to `app/components`. If you wish to use any of them you will need to manually include a script/file reference to the relevant source files.

Example:

    
    

If installing a dependency which has its own dependencies described, these dependencies will also be pulled in.

Example:

will actually also install Underscore.js and jQuery.js as these are required for Backbone to function correctly.

`yeoman install` also supports installing packages using more than just the package name. Namely:

    yeoman install jquery
    yeoman install git://github.com/components/jquery.git
    yeoman install components/jquery (same as above)
    yeoman install http://foo.com/jquery.awesome-plugin.js
    yeoman install ./repos/jquery
    

Packages can be installed by name, Git endpoint, GitHub shorthand, URL or local path. If you install and URL that is a zip or tar file, yeoman will automatically extract the contents of it. When tags are available in the endpoint, you can specify a semver tag to fetch concrete versions:

    yeoman install jquery#1.8.1
    yeoman install git://github.com/components/jquery.git#~1.8.1
    yeoman install components/jquery#1.8.x
    

More in the [Bower docs][4]

Usage: `yeoman list`

Lists all of the packages that have been installed using `yeoman install` (Bower) in your current project.

Example:

    # If you have previously called
    yeoman install backbone
    
    # and then run
    yeoman list
    
    # the output will be
    
    /myapp/
    ├─┬ backbone#0.9.2
    │ ├── jquery#1.7.2
    │ └── underscore#1.3.3
    ├── jquery#1.7.2
    └── underscore#1.3.3
    

As you can see, this also includes the version information for each package and its dependencies.

Usage: `yeoman lookup `

Performs a lookup in the Bower registry for a package of a specific name. One would use this to confirm that a package exists under a specific name (e.g `jquery`), otherwise `search` should be used for broader queries.

Example:

    yeoman lookup jquery
    
    # outputs
    
    jquery git://github.com/maccman/package-jquery.git
    

Usage: `yeoman search `

Searches the Bower registry for packages which include a specific keyword in their name.

Example:

    yeoman search jquery
    
    # outputs
    
    Search results:
    
      - jquery git://github.com/maccman/package-jquery.git
      - jquery-ui git://github.com/maccman/package-jquery-ui.git
      - jquery-infinite-scroll git://github.com/paulirish/infinite-scroll.git
    

Usage: `yeoman update `

Updates an already installed package `packageName` to the latest version available in the Bower registry.

Example:

    yeoman update jquery
    
    # outputs
    bower checking out jquery#v1.7.2
    

The `update` command will also update any other packages in your project relying on this dependency to use this most recent version if any update is applied.

Usage: yeoman uninstall packageName

Removes the package `packageName` from the current project.

Example:

    yeoman uninstall backbone
    
    # outputs:
    
    bower uninstalling /project/components/backbone
    

Note: If you attempt to uninstall a package that is a dependency of other packages, yeoman (via Bower) will throw an error.

Example:

    yeoman uninstall jquery
    
    # outputs:
    warning backbone depends on jquery
    

This simply means that you should uninstall backbone (the top-level package with the dependency) if you wish to remove all traces of the jquery package. Included file 'yeoman.wiki/docs/commands/Generators.md' not found in \_includes directory Included file 'yeoman.wiki/docs/commands/Modules.md' not found in \_includes directory


 [1]: https://github.com/gruntjs/grunt
 [2]: https://github.com/jrburke/r.js
 [3]: http://livereload.com
 [4]: https://github.com/twitter/bower/blob/master/README.md#usage
