node-sublime-build
==================
## Run, stop and restart node and node-inspector from Sublime Text 2

Great tools to do the job are [node-dev](https://github.com/fgnass/node-dev), [node-supervisor](https://github.com/isaacs/node-supervisor) or [node-nodemon](https://github.com/remy/nodemon), for example.
They watch your files and run node when a file changed.

Being old-school, I want to exercise more control about when to (re)start node and the inspector, and 
in which debug mode. That's why I wrote two tiny scripts (besides that I didn't know about the aforementioned
tools when I started scripting :)

------------------

The two scripts and the custom build config are placed in    
	~/Library/Application Support/Sublime Text 2/Packages/User/Build

An entry _custom_ will show up in ST2's _Tools/Build System_ menu.

Hotkeys are enabled by manually editing ST2's user key bindings:

	[
		{ "keys": ["super+ctrl+r"], "command": "build", "args": {"variant": "Run"} },
		{ "keys": ["super+ctrl+u"], "command": "build", "args": {"variant": "Debug"} },
		{ "keys": ["super+ctrl+x"], "command": "build", "args": {"variant": "Debug-Brk"} },
		{ "keys": ["super+ctrl+q"], "command": "build", "args": {"variant": "Stop"} }	
	]

The `run` script calls a [gruntfile](http://gruntjs.com/) to package the HTML 
templates into a single file, from which each view of a SPA fetches its portion.

It also calls [browserify](http://browserify.org/) to create a package of JavaScripts (no AMD right now). 

The whole thing may easily be adapted to specific configurations, say removing grunt or browserify or giving
the server.js another name. I use it together with my work-in-progress [project-template](https://github.com/axelw/project-template)


## Known knowns

- the file called by node is assumed to be named `server.js`. This is because I want to (re)start node without having to switch 
to a certain file in the editor. I *believe* using '$file' wouldn't help, I didn't verify that.
- works on my machine running MacOS 10.7.5. It may or may not work elsewhere


#### Sublime plugins

- [Package Control](http://wbond.net/sublime_packages/package_control)
- [Comments Aware Enter](https://github.com/Suor/CommentsAwareEnter )
- [Markdown Preview](https://github.com/revolunet/sublimetext-markdown-preview.git)
