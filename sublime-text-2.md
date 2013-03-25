[Sublime Text 2](http://www.sublimetext.com/2)
=======================================
The most amazing tool and here some userful packages
## Setup
#### linux
    >sudo add-apt-repository ppa:webupd8team/sublime-text-2
    >sudo apt-get update && sudo apt-get install sublime-text-2
    >packer -S sublime-text-2 (arch)
    
#### osx and windows
   >goto [sublimetext.com](http://www.sublimetext.com/2) and download
   
#### [package control](http://wbond.net/sublime_packages/package_control)
> ctrl + ` (not the tick ' but the other one under the tilde.) and paste below code in command line at bottom. 
```
import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print('Please restart Sublime Text to finish installation')
```
>reboot and install packages: 
>ctrl + shift + p and type Package Install  also Package list,  Package upgrade

## Sync between work/home/linux/osx/win
>mkdir &lt;Dropbox&gt;/Apps/sublime
#### Linux:
    mv ~/.config/sublime-text-2/Packages ~/Dropbox/Apps/sublime
    ln -s ~/Dropbox/Apps/sublime/Packages ~/.config/sublime-text-2/
#### OSX:
    mv ~/Library/Application\ Support/Sublime\ Text\ 2/Packages ~/Dropbox/Apps/sublime/Packages
    ln -s ~/Dropbox/apps/sublime/Packages ~/Library/Application\ Support/Sublime\ Text\ 2/Packages
####Windows
    mklink /D “C:\Users\ra\AppData\Roaming\Sublime Text 2\Packages” “C:\Users\ra\Dropbox\Apps\sublime\Packages"

### key mappings

| keys                   |   description|
|----------------------- | -----------: |
|ctrl+shift+p            |   command pallete: package install, package list, package upgrade|
|shift+alt+1             |   standard view - 1 column layout|
|shift++alt+2            |   2 column layout|
|shift+alt+8             |   2 row layout |
|ctrl+p                  |   #  in html file to get DOM drop down|
| ctrl+p :LINE_NUMBER    |      goto line number|
|ctrl+shift+c            |    colorpicker                 |

### Useful Packages
__utilities:__ git,git ignore, BracketHighlighter, ColorHighlighter,  compass, docblockr,pretty json, colorpicker

[SideBarEnhancements](https://github.com/titoBouzout/SideBarEnhancements)

[SublimeCodeIntel](https://github.com/Kronuz/SublimeCodeIntel) "shift+ctrl+space"  trigger autocomplete manually

__code and syntax:__ dotfilesyntaxhighlighter, puppet, SublimeLinter, Sublime-HTMLPrettify, tag

__snippets:__ gist, casperjs, backbonejs,angularjs, angularjs attributes completion,bourbon and neat autocompletions, cdnjs, jQuery Snippets pack

__themes:__ phoenix, soda, themr, DobDark, Helios
```
[theme-phoenix](http://netatoo.github.com/phoenix-theme/) 
"phoenix_color_darkblue": true,
"phoenix_highlight_current_tab": true    or "phoenix_solid_current_tab": true
"phoenix_dirty_bottom_bar_red": true
"phoenix_sidebar_tree_large": true  or small, medium, xlarge
"phoenix_color_expanded_folder": true
"phoenix_tabs_small": true
"color_scheme": "Packages/Theme - Phoenix/Color Scheme/Tomorrow-Night.tmTheme"
"phoenix_solid_current_tab": true,
```
### User Preferennces
```
{
    "_font_face": "Ubuntu Mono",
	"bold_folder_labels": true,
	"color_scheme": "Packages/DobDark Color Scheme/Dobdark.tmTheme",
	"find_selected_text": true,
	"folder_exclude_patterns":
	[
		".svn",
		".git",
		".hg",
		"CVS",
		"_build",
		"dist",
		"build",
		"site"
	],
	"font_face": "Source Code Pro",
	"font_options":
	[
		"subpixel_antialias"
	],
	"font_size": 13.0,
	"highlight_line": true,
	"highlight_modified_tabs": true,
	"ignored_packages":
	[
		"Vintage"
	],
	"save_on_focus_lost": true,
	"tab_size": 2,
	"theme": "Nil.sublime-theme",
	"translate_tabs_to_spaces": true
}
```

### Side Bar.sublime-menu
```
[
	{"id": "side-bar-files-open-with",
		"children":
		[

			//application 1
			{
				"caption": "gimp",
				"id": "side-bar-files-open-with-gimp",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "gimp", // OSX
									"extensions":"psd"  //any file with these extensions
								}
			},
			{
				"caption": "pinta",
				"id": "side-bar-files-open-with-pinta",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "pinta", // OSX
									"extensions":"jpg|png|gif"  //any file with these extensions
								}
			},
			{
				"caption": "inkscape",
				"id": "side-bar-files-open-with-inkscape",
				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "inkscape", // OSX
									"extensions":"svg"  //any file with these extensions
								}
			},

			//separator
			{"caption":"-"},		
			// browswers
			{
				"caption": "Chrome",
				"id": "side-bar-files-open-with-chrome",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "google-chromee",
									"extensions":"html|php" //any file with extension
								}
			},
			{
				"caption": "Firefox",
				"id": "side-bar-files-open-with-firefox",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "firefox",
									"extensions":"html|php" //any file with extension
								}
			}

			{"caption":"-"}
		]
	}
]
```
