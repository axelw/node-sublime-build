node-sublime-build
==================
## Run and debug node from Sublime Text 2

Two scripts that enable running, debugging and stopping node from within Sublime Text 2 on a Mac.

==================

The two scripts and the custom build config (or symbolic links to these) are to be placed in    
	~/Library/Application Support/Sublime Text 2/Packages/User/Build

An entry _custom_ will show up in ST2's _Tools/Build System_ menu.

Hotkeys may be enabled by manually editing ST2's user key bindings:

	[
		{ "keys": ["super+ctrl+r"], "command": "build", "args": {"variant": "Run"} },
		{ "keys": ["super+ctrl+u"], "command": "build", "args": {"variant": "Debug"} },
		{ "keys": ["super+ctrl+x"], "command": "build", "args": {"variant": "Debug-Brk"} },
		{ "keys": ["super+ctrl+q"], "command": "build", "args": {"variant": "Stop"} }	
	]

The `run` script calls a [gruntfile](http://gruntjs.com/) to package the HTML 
templates into a single file, from which each view of a SPA fetches its portion.

It also calls [browserify](http://browserify.org/) to create a package of JavaScripts (no AMD right now). 

The script calls the OSX function 'open' to activate node-inspector for backend debugging and a site for frontend debugging.


## Known knowns

- the file called by node is assumed to be named `server.js`, located in a folder `server` underneath the ST2 project folder.
- works on my machine running MacOS 10.9.3 It may or may not work elsewhere.


#### Sublime plugins I use

- [Package Control](http://wbond.net/sublime_packages/package_control)
- [Comments Aware Enter](https://github.com/Suor/CommentsAwareEnter )
- [Markdown Preview](https://github.com/revolunet/sublimetext-markdown-preview.git)

#### Alternatives

Tools exist to watch for changes in your sources and make node restart - like [node-dev](https://github.com/fgnass/node-dev), [node-supervisor](https://github.com/isaacs/node-supervisor), or [node-nodemon](https://github.com/remy/nodemon). I never used them, but I guess they may be worth trying.

