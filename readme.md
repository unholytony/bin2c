[![Build status](https://ci.appveyor.com/api/projects/status/4yjvhauivwk0wgex?svg=true)](https://ci.appveyor.com/project/AraHaan/bin2c)
[![Build Status](https://api.travis-ci.org/AraHaan/bin2c.svg?branch=master)](https://travis-ci.org/AraHaan/bin2c)
[![Build status](https://doozer.io/badge/AraHaan/bin2c/buildstatus/master)](https://doozer.io/user/arahaan/bin2c)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/3aab1e403474490aaacaa1a2883ccf8a)](https://www.codacy.com/app/AraHaan/bin2c?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=AraHaan/bin2c&amp;utm_campaign=Badge_Grade)
[![GitHub watchers](https://img.shields.io/github/watchers/arahaan/bin2c.svg)](https://github.com/AraHaan/bin2c/watchers)
[![GitHub forks](https://img.shields.io/github/forks/arahaan/bin2c.svg)](https://github.com/arahaan/bin2c/network)
[![Github Releases](https://img.shields.io/github/release/arahaan/bin2c.svg)](https://github.com/arahaan/bin2c/releases)
[![GitHub stars](https://img.shields.io/github/stars/arahaan/bin2c.svg)](https://github.com/arahaan/bin2c/stargazers)
[![GitHub license](https://img.shields.io/badge/license-MIT-orange.svg)](https://raw.githubusercontent.com/weiboad/adbase/master/LICENSE)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/778/badge)](https://bestpractices.coreinfrastructure.org/projects/778)
[![freenode](https://img.shields.io/badge/chat-on%20freenode-brightgreen.svg)](https://webchat.freenode.net/)

> This program takes any sort of binary file (such as a PNG image file) and processes it into a file that contains its data in a C array allowing it to be embedded in the contents of a program.

The Channel is #bin2c on freenode so be sure to do ``/JOIN #bin2c`` on the main status part of freenode.

bin2c v0.15.0 - Windows/Linux/MAC - [FINAL]:

Windows (Requires Visual Studio 2015 or newer with command line tools):

- open bin2c.sln in Visual Studio 2015 or newer.

- select the configuration platform you want and Build the Release Configuration. You can pick 32 or 64 bit.

- then open the Developer Command Prompt x86 (for 32-bit compile) or x64 (for 64-bit compile).

- and then to build the tests create a batch file named compile.bat in the folder you downloaded bin2c to with this content:
```cmd
@echo off
cd tests
..\\Release\\bin2c.exe /custvar "IMAGE_VP" /nohead /infile ".\\VP.jpg" /outfile ".\\VP.hpp"
cl.exe /nologo /Ox /Tp "VP.cpp" /link /NOLOGO /OUT:"VP.exe" /SUBSYSTEM:CONSOLE /FIXED
cd ..
```

- after the file is (compile.bat) created maximize the Developer command prompt(s) you opened and type in:
```cmd
cd path\to\where\you\downloaded\bin2c
path\to\where\you\downloaded\bin2c>compile.bat
```

This *should* Generate working tests.

*Note: since v0.2.0 the generated output will contain the name of the original files.*

MAC:

- To build you need either gcc/g++ 6.3.0 (or latest) or clang 3.9.1 (or latest).

*Also you need latest libc++ and you also need libc++experimental. Both of which can be obtained from ``brew install llvm``.*

*Note: Don't forget to use the rc file. (which might need some changes) This should hopefully allow you to have a resource section.*
*Also Since I do not work for apple nor do I even own a mac I do not know for sure how to compile an resoruce script on a mac for a .rsrc section on the compiled binary.*

Linux:

- To build you need either gcc/g++ 6.3.0 (or latest) or clang 3.9.1 (or latest).

*I assume you have the libstdc++fs library for <experimental/filesystem> to work on most linux distributions.*
