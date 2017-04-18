The repository is only for building and installing GridLAB-D from source.  The 
installers for released versions are available at http://sourceforge.net/projects/gridlab-d/files/.

# Installing from source

Download the source code, build, install and validate (you will need autotools)
```
  host% git clone git@code.stanford.edu:/gridlabd/gridlabd source
  host% cd source
  host% autoreconf -isf
  host% ./configure --enable-silent-rules --prefix=$HOME 'CXXFLAGS=-w' 'CFLAGS=-w'
  host% make install
  host% export PATH=~/bin:$PATH
  host% gridlabd --validate
```

## Windows build

Windows users will need to install cygwin to enable building using autotools.
See [Windows build instructions](http://gridlab-d.sourceforge.net/wiki/index.php/MinGW/Eclipse_Installation)
for details.

## Mac OSX build

1. Install 'brew' if you have not already done so:
```
  host% /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

2. Install required tools, if they are not already installed:
```
  host% brew install automake
  host% brew install gcc
  host% brew install git
  host% brew install wget
  host% brew install xerces-c
```
Depending on the specifics of your machine, you may need to install additional dependencies.

3. If you plan on using mysql, install it:
```
  host% brew install mysql
```
and follow the instructions for [setting up MySQL for GridLAB-D](http://gridlab-d.sourceforge.net/wiki/index.php/Mysql#Prerequisites).

4. Clone the SLAC deployment of GridLAB-D:
```
  host% mkdir ~/gridlabd
  host% cd ~/gridlabd
  host% git clone https://github.com/dchassin/gridlabd-slac source
```

5. Build, install and validate GridLAB-D:
```
  host% cd ~/gridlabd/source
  host% autoreconf -isf
  host% ./configure --enable-silent-rules --prefix=/usr/local 'CXXFLAGS=-w -O2' 'CFLAGS=-w -O2'
  host% make install
  host% gridlabd --validate
```

Note: On some system you must install GNU-sed if the build fails on something to do with 'sed':
Install gnu sed
```
  host% brew install --with-default-names gnu-sed
```

## Eclipse Development Environment Setup

You can setup Eclipse as your GridLAB-D modeling editor.  See 
[Eclipse setup instructions](http://gridlab-d.sourceforge.net/wiki/index.php/Eclipse) for details.

# Online Documentation

The primary manuals for GridLAB-D are online at Main Page for GridLAB-D (http://gridlab-d.sourceforge.net/wiki/index.php/Main_Page).
Documentation of local projects can be found on this project's wiki (https://code.stanford.edu/gridlabd/gridlabd/wikis/home).
