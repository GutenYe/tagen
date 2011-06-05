Tagen, a core and extra extension to Ruby library.
b
a
==========================================

**Homepage**: [https://github.com/GutenLinux/tagen](https://github.com/GutenLinux/tagen) <br/>
**Author**: 	Guten <br/>
**Contributors**: See Contributors section below  <br/>
**License**: MIT License <br/>
**Documentation**: [http://rubydoc.info/gems/tagen/frames](http://rubydoc.info/gems/tagen/frames) <br/>
**Issue Tracker**: [https://github.com/GutenLinux/tagen/issues](https://github.com/GutenLinux/tagen/issues) <br/>

Overview
--------

Ruby has an 'Open Class' feature, so we can extend any class by ourself.

This library provides some usefull Ruby core extension.  some comes from ActiveSupport. ActiveSupport is mainly target to Rails, but tagen is target to generic ruby development, and tagen is smaller. It is a colletion of most common core,extra extensions.

This library comes with a path lib named {Pa} and a string format lib named {PyFormat}.

Usage
-----
use core extension

	require "tagen/core"

then we have String#blank? method, for a list of core extensions, see {file:docs/CoreExtensions.md docs/CoreExtensions}.

use extra extension

	require "pathname"
	require "tagen/pathname"

or

	require "tagen/pathname" # auto require "pathname"

this will add #path method to Pathname, see API doc.

Requirements
------------

	tested: ruby1.9 linux

An Introduction to Pa 
---------------------

	require "tagen/core"
	pa = Pa('/home/foo')
	pa.exists? #=> false
	pa.dir #=> '/home'
	pa.base #=> 'foo'
	pa.join('a.ogg') #=> '/home/a.ogg'
	pa.join(a.ogg).exists? #=> true.

	Pa.exists?('/home/foo') # alternate way

which rspec

	Pa('/home/foo').should be_exists

more see API doc

An Introduction to PyFormat
---------------------------

	require "tagen/core"
	"I like %{fruit} and %{sport}".format('apple', 'football') 
	"I like %{fruit} and %{sport}".format(apple: 'apple', footbal: 'football') 

	"it costs %{howmatch:.2f} dollars".format(1.123) #=> "it costs 1.12 dollars"
	
more see API doc


Documentation
-------------
* {file:docs/CoreExtensions.md CoreExtensions} A list of core extensions.
* {file:docs/ExtraExtensions.md ExtraExtensions} A list of extra extensions.
* {file:docs/Architecture.md Architecture} Source code architecture.

Install
----------
	gem install tagen

Contributing
-------------
* report bugs/featues to issue tracker.
* fork it and pull a request.
* improve documentation.
* any ideas are welcome.

Contributors
------------

WORD-III
this is me


Copyright
---------
Copyright &copy; 2011 by Guten. this library released under MIT-License, See {file:LICENSE} for futher details.
