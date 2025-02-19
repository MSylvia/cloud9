# Cloud9 IDE

> **NOTE:** This is my fork of the Cloud9 IDE v2

Cloud9 is an open source IDE built with [Node.JS] on the back-end and JavaScript/HTML5 on the client.
It is very actively maintained by about 20 developers in both Amsterdam and San Francisco and is one
component of the hosted service at [c9.io](http://c9.io). The version available here runs on your local system.

Cloud9 balances the power of traditional desktop IDEs with the simplicity and elegance of editors
like TextMate and Sublime.

Cloud9 is built entirely on a web stack, making it the most hacker-friendly IDE today.
Fork it, hack it, and if you think others would benefit, issue a pull request on this repo
and we'll take a look. If you have any questions, meet us in #cloud9ide on irc.freenode.net
or ask us on Twitter [@Cloud9IDE](http://twitter.com/#!/Cloud9IDE).

Happy Coding!

## Features

  * High performance ACE text editor with bundled syntax highlighting support for JS, HTML, CSS and mixed modes.
  * Integrated debugger for [Node.JS] applications with views of the call stack, variables, live code execution and live inspector
  * Advanced Javascript language analysis marking unused variables, globals, syntax errors and allowing for variable rename
  * Local filesystem is exposed through [WebDAV](http://en.wikipedia.org/wiki/WebDAV) to the IDE, which makes it possible to connect to remote workspaces as well
  * Highly extensible through both client-side and server-side plugins
  * Sophisticated process management on the server with evented messaging

## Browser Support

We support the newer versions of Chrome, Firefox and Safari.

## Installation and Usage

If installing on Windows, please refer to [Installation on Windows](#installation-on-windows-experimental).

Requirements:

  * NodeJS `>= 0.6.16`
  * NPM `>= 1.1.16`
  * libxml2-dev

Install:

    git clone https://github.com/ajaxorg/cloud9.git
    cd cloud9
    npm install

The above install steps create a `cloud9` directory with a `bin/cloud9.sh`
script that can be used to start Cloud9:

    bin/cloud9.sh

Optionally, you may specify the directory you'd like to edit:

    bin/cloud9.sh -w ~/git/myproject

Cloud9 will be started as a web server on port `-p 3131`, you can access it by
pointing your browser to: [http://localhost:3131](http://localhost:3131)

By default Cloud9 will only listen to localhost.
To listen to a different IP or hostname, use the `-l HOSTNAME` flag.
If you want to listen to all IP's:

    bin/cloud9.sh -l 0.0.0.0

If you are listening to all IPs it is adviced to add authentication to the IDE.
You can either do this by adding a reverse proxy in front of Cloud9,
or use the built in basic authentication through the `--username` and `--password` flags.

    bin/cloud9.sh --username leuser --password c9isawesome

Cloud9 is compatible with all connect authentication layers,
to implement your own, please see the `plugins-server/cloud9.connect.basic-auth` plugin
on how we added basic authentication.

## Installation on Windows (experimental)

If you're running Cloud9 on Windows you'll have to follow these steps as well:

  * Install [Grep for Windows](http://gnuwin32.sourceforge.net/downlinks/grep.php)
  * Add `C:\Program Files (x86)\GnuWin32\bin` to your [PATH](http://www.computerhope.com/issues/ch000549.htm)
  * Open a new instance of `cmd` with elevated rights (right click 'Run as adminstrator')
  * Now follow the steps under 'Install'
  * *Please note that the `npm install` fails due to a libxml error, but you can ignore that for now.*

To start Cloud9, please don't start through `bin/cloud9.sh` but rather via:

    node server.js [args]

Please note that there will be errors displayed regarding the `find` command,
and that some features might not work.
Feel free to improve the Windows experience and open a pull request.

## Updating

To update to the latest version (if this doesn't work, just make a fresh clone):

    git pull
    npm update

`npm update` does not currently install missing dependencies. To do so use:

    npm install

## Open Source Projects Used

The Cloud9 IDE couldn't be this cool if it weren't for the wildly productive
[Node.JS] community producing so many high quality software.
Main projects that we use as building blocks:

  * [async.js] by [fjakobs]
  * [jsDAV] by [mikedeboer]
  * [connect] by [senchalabs](http://github.com/senchalabs)
  * [engine.io] by [LearnBoost](http://github.com/LearnBoost)
  * [smith.io](http://github.com/c9/smith.io) by [creationix](http://github.com/creationix) & [cadorn](http://github.com/cadorn)
  * [ace](http://github.com/ajaxorg/ace) by [fjakobs]
  * [apf](http://www.ajax.org) by [ajax.org]
  * and of course [Node.JS]!

Thanks to all developers and contributors of these projects!

[fjakobs]: http://github.com/fjakobs
[javruben]: http://github.com/javruben
[mikedeboer]: http://github.com/mikedeboer
[ajax.org]: http://www.ajax.org/
[async.js]: http://github.com/fjakobs/async.js
[jsDAV]: http://github.com/mikedeboer/jsdav
[connect]: http://github.com/senchalabs/connect
[engine.io]: http://github.com/LearnBoost/engine.io
[requireJS]: http://requirejs.org/
[Node.JS]: http://nodejs.org/

## License

The GPL version 3, read it at [http://www.gnu.org/licenses/gpl.txt](http://www.gnu.org/licenses/gpl.txt)
