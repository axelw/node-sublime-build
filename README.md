node-sublime-build
==================
## Running node and node-inspector from Sublime Text 2

The two scripts and the custom build config are placed in    
	~/Library/Application Support/Sublime Text 2/Packages/User/Build

An entry _custom_ will show up in ST2's _Tools/Build System_ menu.

Hotkeys are enabled by manually editing ST2's key bindings:

	[
		{ "keys": ["super+ctrl+r"], "command": "build", "args": {"variant": "Run"} },
		{ "keys": ["super+ctrl+u"], "command": "build", "args": {"variant": "Debug"} },
		{ "keys": ["super+ctrl+q"], "command": "build", "args": {"variant": "Stop"} },
		{ "keys": ["super+ctrl+x"], "command": "build", "args": {"variant": "Debug-Brk"} }
	]

The `run` script calls a [gruntfile](http://http://gruntjs.com/) to package the HTML 
templates into a single file, from which each view of a SPA fetches its portion.

It also calls [browserify](http://browserify.org/) to create a package of JavaScripts (no AMD right now). 

So the whole thing is useful when working on a [project-template](https://github.com/axelw/project-template)


## Known knowns

- the file called by node is assumed to be named `server.js`
- works on my machine running MacOS 10.7.5. It may or may not work elsewhere


#### Sublime plugins

- [Package Control](http://wbond.net/sublime_packages/package_control)
- [Comments Aware Enter](https://github.com/Suor/CommentsAwareEnter )
- [Markdown Preview](https://github.com/revolunet/sublimetext-markdown-preview.git)
