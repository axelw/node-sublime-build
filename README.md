node-sublime-build
==================
## Running node and node-inspector from Sublime Text 2

The two scripts and the custom build config should to be placed in    ~/Library/Application Support/Sublime Text 2/Packages/User/Build

An entry _custom_ will show up in ST2's _Tools/Build System_ menu.

Hotkeys are enabled via ST2's key bindings:

	[
		{ "keys": ["super+ctrl+r"], "command": "build", "args": {"variant": "Run"} },
		{ "keys": ["super+ctrl+u"], "command": "build", "args": {"variant": "Debug"} },
		{ "keys": ["super+ctrl+q"], "command": "build", "args": {"variant": "Stop"} },
		{ "keys": ["super+ctrl+x"], "command": "build", "args": {"variant": "Debug-Brk"} }
	]

## Known caveats & issues

- this build system assumes that the file called by node goes by the name of `app.js`
- it works on my machine running MacOS 10.7.5. It may work elsewhere, but nobody knows.
- maybe more :)


