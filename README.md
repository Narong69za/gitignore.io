<p align="center">
    <a href="https://www.toptal.com/developers/gitignore">
        <img src="Public/img/gitignoreio.svg"/>
    </a>
    <br>
    <strong>Create useful .gitignore files for your project</strong>
</p>
<p align="center">
<<<<<<< HEAD
    <a href="https://swift.org"><img src="https://img.shields.io/badge/Swift-4.1-orange.svg?style=flat-square"/></a>
    <a href="https://travis-ci.org/toptal/gitignore.io"><img src="https://img.shields.io/travis/toptal/gitignore.io/master?style=flat-square" alt="Travis"></a>
    <a href="https://codeclimate.com/github/joeblau/gitignore.io/test_coverage"><img src="https://img.shields.io/codeclimate/coverage/joeblau/gitignore.io.svg?style=flat-square" alt="Code Climate Test Coverage"></a>
    <a href="https://codeclimate.com/github/joeblau/gitignore.io/maintainability"><img src="https://img.shields.io/codeclimate/maintainability/joeblau/gitignore.io.svg?style=flat-square" alt="Code Climate Maintainability"></a>
    <img src="https://img.shields.io/badge/Platforms-Linux%20%7C%20macOS%20%7C%20Windows-blue.svg?style=flat-square"alt="Platforms">
    <a href="https://github.com/joeblau/gitignore.io/blob/master/LICENSE.md"><img src="https://img.shields.io/github/license/joeblau/gitignore.io.svg?style=flat-square" alt="license"></a>
</p>

## About
=======
    <a href="https://travis-ci.org/joeblau/gitignore.io">
        <img src="https://img.shields.io/travis/joeblau/gitignore.io.svg"
             alt="Travis">
    </a>
    <a href="https://nodejs.org">
        <img src="https://img.shields.io/badge/node-%3E%3D5.0.0-orange.svg"
             alt="node">
    </a>
    <a href="https://www.npmjs.com">
        <img src="https://img.shields.io/badge/npm-%3E%3D3.3.6-orange.svg"
             alt="npm">
    </a>
    <a href="https://bower.io">
        <img src="https://img.shields.io/bower/v/bootstrap.svg"
             alt="Bower">
    </a>
    <a href="https://david-dm.org/joeblau/gitignore.io">
        <img src="https://img.shields.io/david/joeblau/gitignore.io.svg"
             alt="David">
    </a>
    <a href="https://david-dm.org/joeblau/gitignore.io#info=devDependencies">
        <img src="https://img.shields.io/david/dev/joeblau/gitignore.io.svg"
             alt="David">
    </a>
    <img src="https://img.shields.io/badge/Platforms-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey.svg"
          alt="Platforms">
    <a href="https://github.com/joeblau/gitignore.io/blob/master/LICENSE.md">
        <img src="https://img.shields.io/github/license/joeblau/gitignore.io.svg"
             alt="license">
    </a>
</p>

# Install Command Line

To run gitignore.io from your command line you need an active internet connection and an environment function. You need to add a function to your environment that lets you access the gitignore.io API.

## Git
`#!/bin/bash`
```sh
$ git config --global alias.ignore '!gi() { curl -L -s https://www.gitignore.io/api/$@ ;}; gi'
```

## Linux
`#!/bin/bash`
```sh
$ echo "function gi() { curl -L -s https://www.gitignore.io/api/\$@ ;}" >> ~/.bashrc && source ~/.bashrc
```

`#!/bin/zsh`
```sh
$ echo "function gi() { curl -L -s https://www.gitignore.io/api/\$@ ;}" >> ~/.zshrc && source ~/.zshrc
```

## macOS
`#!/bin/bash`
```sh
$ echo "function gi() { curl -L -s https://www.gitignore.io/api/\$@ ;}" >> ~/.bash_profile && source ~/.bash_profile
```
`#!/bin/zsh`
```sh
$ echo "function gi() { curl -L -s https://www.gitignore.io/api/\$@ ;}" >> ~/.zshrc && source ~/.zshrc
```

## Windows
Create a PowerShell v3 Script
```posh
#For PowerShell v3
Function gig {
  param(
    [Parameter(Mandatory=$true)]
    [string[]]$list
  )
  $params = $list -join ","
  Invoke-WebRequest -Uri "https://www.gitignore.io/api/$params" | select -ExpandProperty content | Out-File -FilePath $(Join-Path -path $pwd -ChildPath ".gitignore") -Encoding ascii
}
```
Create a PowerShell v2 Script
```posh
#For PowerShell v2
Function gig {
  param(
    [Parameter(Mandatory=$true)]
    [string[]]$list
  )
  $params = $list -join ","
  $wc = New-Object System.Net.WebClient
  $wc.Headers["User-Agent"] = "PowerShell/" + $PSVersionTable["PSVersion"].ToString()
  $wc.DownloadFile("https://www.gitignore.io/api/$params", "$PWD\.gitignore")
}
```

Create a Command Line Prompt Script
If you have installed [msysgit](http://msysgit.github.io)), create `gi.cmd` with content below. And copy it to `C:\Program Files\Git\cmd\gi.cmd`, assuming `msysgit` was installed to `c:\Program Files\Git`. Make sure that `C:\Program Files\Git\cmd` is added to the environment variable `path`.
```bat
@rem Do not use "echo off" to not affect any child calls.
@setlocal

@rem Get the abolute path to the parent directory, which is assumed to be the
@rem Git installation root.
@for /F "delims=" %%I in ("%~dp0..") do @set git_install_root=%%~fI
@set PATH=%git_install_root%\bin;%git_install_root%\mingw\bin;%PATH%

@if not exist "%HOME%" @set HOME=%HOMEDRIVE%%HOMEPATH%
@if not exist "%HOME%" @set HOME=%USERPROFILE%

@curl.exe -L -s https://www.gitignore.io/api/%*
```
## Other Clients

Clients maintained by third-party developers

| Source Code | Language | Instructions | Maintainer |
|---|---|---|---|
| [gogi](https://github.com/Gnouc/gogi) | Go | [Install](https://github.com/Gnouc/gogi#installation) | [Cuong Manh Le](https://github.com/Gnouc) |
| [ignr](https://github.com/Antrikshy/ignr.py) | Python | [Usage](https://github.com/Antrikshy/ignr.py#usage) | [Antriksh Yadav](https://github.com/Antrikshy) |

Tools or extensions maintained by third-party developers on other platforms

| Source Code | Platform | Instructions | Maintainer
|---|---|---|---|
| [fzf-gitignore](https://github.com/fszymanski/fzf-gitignore.nvim) | Neovim | [Install](https://github.com/fszymanski/fzf-gitignore.nvim#installation) | [Filip Szymański](https://github.com/fszymanski)
| [gi](https://marketplace.visualstudio.com/items?itemName=rubbersheep.gi) | Visual Studio Code | [Install](https://marketplace.visualstudio.com/items?itemName=rubbersheep.gi#install) | [Hasit Mistry](https://github.com/hasit/)
| [helm-gitignore](https://github.com/jupl/helm-gitignore) | GNU Emacs | [Install](https://github.com/jupl/helm-gitignore#installation) | [Juan Placencia](https://github.com/jupl)

# Use Command Line

After the function is created, the `gi` command will give you command line access to the gitingore.io API. . **Note:** Use `gig` if you are on Windows

## View
Show output on the command line. **Note:** Use `gig` if you are on Windows
```sh
$ gi linux,java
# Created by https://www.gitignore.io

### Linux ###
.*
!.gitignore
*~

### Java ###
*.class
# Package Files #
*.jar
*.war
*.ear
```

## Global
Append Operating System and IDE settings to global .gitignore. **Note:** Use `gig` if you are on Windows
```sh
$ gi linux,eclipse >> ~/.gitignore_global
```

## Project
Appending Programming Langauge settings to your projects .gitignore. **Note:** Use `gig` if you are on Windows
```sh
$ gi java,python >> .gitignore
```

## List
List displays a list of all of the currently support gitignore.io templates. **Note:** Use `gig` if you are on Windows
```sh
$ gi list
actionscript,ada,agda,android,appceleratortitanium,appcode,archives,
archlinuxpackages,autotools,bancha,basercms,bower,bricxcc,c,c++,cakephp,
cfwheels,chefcookbook,clojure,cloud9,cmake,codeigniter,codekit,commonlisp,
compass,composer,concrete5,coq,cvs,dart,darteditor,delphi,django,dotsettings,
dreamweaver,drupal,eagle,eclipse,elasticbeanstalk,elisp,elixir,emacs,ensime,
episerver,erlang,espresso,expressionengine,fancy,finale,flexbuilder,forcedotcom,
freepascal,fuelphp,gcov,go,gradle,grails,gwt,haskell,intellij,java,jboss,jekyll,
jetbrains,joe,joomla,justcode,jython,kate,kdevelop4,kohana,komodoedit,laravel,
latex,lazarus,leiningen,lemonstand,lilypond,linux,lithium,magento,matlab,maven,
mercurial,meteor,modelsim,monodevelop,nanoc,netbeans,node,notepadpp,objective-c,
ocaml,opa,opencart,openfoam,oracleforms,osx,perl,ph7cms,phpstorm,playframework,
plone,prestashop,processing,pycharm,python,qooxdoo,qt,quartus2,r,rails,redcar,
rhodesrhomobile,ros,ruby,rubymine,rubymotion,sass,sbt,scala,scrivener,sdcc,
seamgen,senchatouch,silverstripe,sketchup,stella,sublimetext,sugarcrm,svn,
symfony,symfony2,symphonycms,tags,target3001,tarmainstallmate,tasm,tex,textmate,
textpattern,turbogears2,typo3,unity,vagrant,vim,virtualenv,visualstudio,vvvv,
waf,wakanda,webmethods,webstorm,windows,wordpress,xamarinstudio,xcode,xilinxise,
yeoman,yii,zendframework
```

# Advanced Command Line Improvements

Advanced command line suggestions are tracked on the [gitignore.io wiki](https://github.com/joeblau/gitignore.io/wiki/Advanced-Command-Line-Improvements).

# Install Locally

## Instructions

In order to install gitignore.io locally, you'll need to have
[a current](https://github.com/nodejs/LTS) version of **node.js** and **npm**
installed.  You also need **git** installed on your machine.

```sh
$ git clone --recursive git@github.com:joeblau/gitignore.io.git
$ cd gitignore.io/
$ npm install
$ node server.js
```


# About
>>>>>>> upstream/node-legacy

.gitignore.io is a web service designed to help you create .gitignore files for
your Git repositories. The site has a graphical and command line method of
creating a .gitignore for your operating system, programming language, or IDE.

## `.gitignore` Template Source

Source templates for gitignore.io: https://github.com/toptal/gitignore

## License of the generated files

All files generated by https://www.toptal.com/developers/gitignore are under [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

## Documentation

Complete gitignore.io documentation: https://docs.gitignore.io/

## Docker Container

### Prerequisites

- [Docker](https://www.docker.com/)

### Build

#### Production

```
docker-compose up --build
```

#### Development

```
docker-compose -f ./docker-compose-dev.yml build
```
```
docker-compose -f ./docker-compose-dev.yml up
```

It will start the web server running on [http://localhost:8080](http://localhost:8080)

Development mode mounts the following directories to docker volumes:

- `/Public`
- `/Resources `

## LESS and CSS

The app uses [LESS](http://lesscss.org/) as its CSS preprocessor for the files in `Public/css`.

To process the less file you need to:

- Install all dependencies with `yarn install`
- Process the assets with `yarn build`

## Environment Variables

Please set your environment variables to docker configurations. All are optional.

```yml
...
services:
  app:
    ...
    environment:
      HOST_ORIGIN: http://www.example.com
      BASE_PREFIX: /foo/bar
      GOOGLE_ANALYTICS_UID:
    ...
...
```

### HOST_ORIGIN

Origin of your web server, falls back to https://www.toptal.com

```
HOST_ORIGIN: http://www.example.com
```

### BASE_PREFIX

If you want to host this web server under a subdirectory (http://www.example.com/foo/bar for example), please set this variable.

```
BASE_PREFIX: /foo/bar
```

### GOOGLE_ANALYTICS_UID

User ID for Google Tag Manager snippet

```
GOOGLE_ANALYTICS_UID: UA-XXXXXXXX-X
```

## E2E Tests

Tests are located in `e2e-tests` folder with:

- API tests in `api` folder - implemented using [Superagent](https://github.com/visionmedia/superagent)
- E2E tests in `pages` folder - implemented with [Puppeteer](https://github.com/puppeteer/puppeteer)

Prerequisites:

- [Node.js](https://nodejs.org/en/) 12.9 or above.
- [Yarn](https://yarnpkg.com/lang/en/) 1.15.2 or 1.17.3

Running:

- Set the BASE_URL env variable (only if you have changed the default URL or port)
- docker-compose up --build --detach
- yarn gitupdate
- yarn install
- yarn build
- yarn test
- docker-compose stop
