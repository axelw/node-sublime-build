node-sublime-build
==================
## Running node and node-inspector from Sublime Text 2

The two bash scripts and the custom build configuration should to be placed in folder   ~/Library/Application Support/Sublime Text 2/Packages/User/Build folder.

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
- when node is started, the `run`script stores the pid in a file. That file is used by the `stop` script. This script tries to ensure that it only stops processes (by sending them SIGTERM) which are started by `run`. In case a process has a pid 5678, but another process has pid 56789, `stop` gets confused, and the node process must be ended manually in the terminal. All this is due to my limited knowledge of regex.
- it works on my machine running MacOS 10.7.5. It may work elsewhere, but nobody knows.


