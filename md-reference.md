Markdown Reference
=========

Quick reference for things github:   
- git commands    
- markdown reference    
- todo   
	- gh_pages   
	- gists   

Git
-----------
```sh
git clone https://github.com/rballen/documents.git 
git clone git://github.com/rballen/documents.git
git clone git@github.com:rballen/documents.git

mkdir repo && cd repo
git init 
git add file1 file
git add .  

git status
git log
git log -n 3  # display last 3 commits
git log --stat  # high level overview

git commit file1 files2...-m 'message'
git commit -a -m "message" # commit all files 

git checkout -b branch
git branch -r

git remote add origin git@github.com:rballen/documents.git
git push -u origin master
git pull
```

#### .gitignore
```
.DS_Store
Desktop.ini
stage
.svn
.*.swp
*.class
*.log
*.dat
npm-debug.log
logs
# intellij
*.iml
*.ipr
*.iws
.idea/

# eclipse
.project
.metadata
bin
.classpath
.settings
.loadpath
.externalToolBuilders
*.launch
```


#### .gitconfig
```
[user]
    name = First Mi. Last
  email = name@email.com
[github]
    user = rballen
[core]
  excludesfile = /home/ra/.gitignore
    editor = /usr/bin/vim
    whitespace=fix,-indent-with-non-tab,trailing-space,cr-at-eol   
[color]
    ui = auto
[color "branch"]
    current = yellow reverse
    local = yellow
    remote = green
[color "diff"]
    meta = yellow bold
    frag = magenta bold
    new = green bold
[alias]
    co = checkout
    ci = commit
    st = status
    br = branch
    hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
    type = cat-file -t
    dump = cat-file -p
    gl = log
```


Github Favored Markdown
--------------
Markdown is a lightweight markup language based on the formatting conventions that people naturally use in email. 
* [markdown website](http://daringfireball.net/projects/markdown/)



```sh
H1
=====================
H2
----------------

# H1
## H2
### H3
#### H4
##### H5
###### H6

| col1      | col2          |  col3         |  col4    |
| --------- |:------------- | -------------:| --------:|
|  row1     | left aligned  | right alinged |   ---    |
|  row2     | left aligned  | right alinged |   ---    |

_italics_  or *italics*
__bold__ or **bold**
___both___ or ***both***

hard return is a line with at least 3 space on end

unordered list
* item
* item
- dash or asterdics

ordered list 
1. item
1. keep using 1
1. last item

[title](url)

warp code inline with `code.....` single apostroph under tilde
multiline with syntax hightling like


```
<pre>
             ,-. 
    ,     ,-.   ,-. 
   / \   (   )-(   ) 
   \ |  ,.>-(   )-< 
    \|,' (   )-(   ) 
     Y ___`-'   `-' 
     |/__/   `-' 
     | 
     | 
     |    -hrr- 
  ___|_____________ 
</pre>
