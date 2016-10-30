---
layout: post
title: Install Python 3.4 Ubuntu 12.04
summary:
status: draft
hn-discussion:
---


This quick tutorial is going to show you how to install Python 3.3.5 (or 3.4.0) and set as default in Ubuntu 12.04

Python 3.3.5 was released on March 9th, 2014. It fixed:

* a 3.3.4 regression in zipimport
* a 3.3.4 regression executing script with a coding declarated and Windows newlines
* potential DOS using compression codecs in bytes.decode()

Python 3.4.0 was released one week later than 3.3.5 with below new features:

* a “pathlib” module providing object-oriented filesystem paths
* a standardized “enum” module
* a build enhancement that will help generate introspection information for builtins
* improved semantics for object finalization
* adding single-dispatch generic functions to the standard library
* a new C API for implementing custom memory allocators
* changing file descriptors to not be inherited by default in subprocesses
* a new “statistics” module
* standardizing module metadata for Python’s module import system
* a bundled installer for the pip package manager
* a new “tracemalloc” module for tracing Python memory allocations
* a new hash algorithm for Python strings and binary data
* a new and improved protocol for pickled objects
* a new “asyncio” module, a new framework for asynchronous I/O

### Install:

A third party launchpad PPA contains older and newer Python version for Ubuntu. The two Python releases are available in the PPA for Ubuntu 14.04 and 12.04.

To add the PPA, Open terminal and run:

> sudo add-apt-repository ppa:fkrull/deadsnakes

You may read the PPA description in the output and then:

Install Python 3.3.5 using the following command:

> sudo apt-get update; sudo apt-get install python3.3

Or install Python 3.4.0 using the following command:

> sudo apt-get update; sudo apt-get install python3.4

To set your installed python as default, run the below commands one by one (You may change python3.3 to python3.4 in the code):


> rm /usr/bin/python && ln -s /usr/bin/python3.4 /usr/bin/python


