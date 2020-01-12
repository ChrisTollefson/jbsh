# `jsonbash` — The JSON Bourne Again Shell

`jsonbash` is a JavaScript shell.


## Installation

TODO


## FAQ

### So it's actually JavaScript, not JSON?

OK, you got me, it's not JSON (at least insofar as [JSON] isn't [JavaScript]).

[JSON]: <https://en.wikipedia.org/wiki/JSON> "Wikipedia: JSON"
[JavaScript]: <https://en.wikipedia.org/wiki/JavaScript> "Wikipedia: JavaScript"


### Then why is it *called JSON* Bourne Again Shell?

I'm not sure what the [`jsonbash`][jsonbash] project does yet, but I'm pretty excited about the name<sup>[[1]][[2]][[3]]</sup>.

[jsonbash]: <https://github.com/ChrisTollefson/jsonbash> "GitHub: ChrisTollefson/jsonbash"
[1]: <https://github.com/searls/matt-daemon/blob/master/README.md> "GitHub: searls/matt-daemon/README.md"
[2]: <https://github.com/bostonaholic/jason-bourne-shell/blob/master/README.md> "GitHub: bostonaholic/jason-bourne-shell/README.md"
[3]: <https://github.com/Breton/json-bourne-shell/blob/master/README.md> "GitHub: Breton/json-bourne-shell/README.md"


### Wait — is this shell just the Node.js REPL?

Yeah.

```Shell
#!/usr/bin/env node
```

[REPL]: <https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop> "Wikipedia: Read-eval-print loop"


### Hasn't that been done before?

[Yes](<https://stackoverflow.com/questions/33850903/use-node-js-as-shell> "Stack Overflow: Use Node.js as Shell").


### So is `jsonbash` basically useless?

AFAICT, yes.


### Then why do this?

For fun, I guess?

But it was prompted by [Apple] [switching] the default [shell] from Bourne Again Shell ([bash]) to Z Shell ([zsh]) as of [macOS] [Catalina (10.15)][Catalina].

#### To go off on an opinionated tangent...

This change in macOS was perhaps due to the [licensing] of GNU Bash: version 4 (2009) and later have been licensed under [GPLv3], whereas version 3 (2004) was licensed under [GPLv2].  One motivation behind version 3 of the [GPL] was to restrict [Tivoization], whereby vendors of hardware (e.g. [TiVo]) would incorporate copyleft-licensed [open-source software] into their products, but use [hardware restriction] (such as digital signatures) to prevent modified versions of that software from running on those products — arguably defeating the [copyleft] purpose of the license.  Even though GNU Bash is already at version 5 (2019), macOS still ships with version 3.2.57 (2007), which was the last version of GNU Bash licensed under GPLv2.  So maybe Apple is gearing up to implement some kind of Tivoization for their own hardware products?  To do so, they couldn't include any GPLv3 code in macOS, which might explain why GNU Bash is stuck at 3.2.57.

But according to http://meta.ath0.com/2012/02/05/apples-great-gpl-purge/, Apple has been removing specifically GPL-licensed software packages from macOS as of [Mac OS X Leopard (10.5)][Leopard] (or earlier?):

| macOS version           | Number of GPL-licensed packages |
|-------------------------|---------------------------------|
| 10.5  — [Leopard]       | 47
| 10.6  — [Snow Leopard]  | 44
| 10.7  — [Lion]          | 29
| 10.8  — [Mountain Lion] | 22
| 10.9  — [Mavericks]     | 19
| 10.10 — [Yosemite]      | 18
| 10.11 — [El Capitan]    | 16
| 10.12 — [Sierra]        | 16

[Leopard]: <https://en.wikipedia.org/wiki/Mac_OS_X_Leopard> "Wikipedia: Mac OS X Leopard"
[Snow Leopard]: <https://en.wikipedia.org/wiki/Mac_OS_X_Snow_Leopard> "Wikipedia: Mac OS X Snow Leopard"
[Lion]: <https://en.wikipedia.org/wiki/Mac_OS_X_Lion> "Wikipedia: Mac OS X Lion"
[Mountain Lion]: <https://en.wikipedia.org/wiki/OS_X_Mountain_Lion> "Wikipedia: OS X Mountain Lion"
[Mavericks]: <https://en.wikipedia.org/wiki/OS_X_Mavericks> "Wikipedia: OS X Mavericks"
[Yosemite]: <https://en.wikipedia.org/wiki/OS_X_Yosemite> "Wikipedia: OS X Yosemite"
[El Capitan]: <https://en.wikipedia.org/wiki/OS_X_El_Capitan> "Wikipedia: OS X El Capitan"
[Sierra]: <https://en.wikipedia.org/wiki/MacOS_Sierra> "Wikipedia: MacOS Sierra"


Maybe that's a coincidence, but the switch to zsh as the default could foreshadow bash's eventual removal from macOS entirely.  It's bad enough that it's already a decade out-of-date, but IMHO, the complete loss of bash would be unfortunate for developers on macOS and for interoperability between operating systems generally.

---

To be fair, Apple doesn't seem to be backing away from open-source; on the contrary, they appear to embrace it, for example, as stated at https://developer.apple.com/opensource/:

> Open source software is at the heart of Apple platforms and developer tools, and Apple continues to contribute and release significant quantities of open source code.

And I would concur, based on some of the open-source projects listed there, or previously hosted at [macOS forge]:

| Project | License |
|---------|---------|
[![github]][github/alac]     [ALAC][www/alac] — Apple Lossless Audio Codec                        | [Apache] (2.0)
[![www]][source/bonjour]     [Bonjour][www/bonjour] mDNSResponder — Zero-configuration networking | [Apache] (2.0)
[![github]][github/cups]     [CUPS][www/cups] — Common UNIX Printing System                       | [Apache] (2.0)
[![www]][source/darwin]      [Darwin][www/darwin] — macOS/iOS core OS                             | partial [APSL]
[![github]][github/macports] [MacPorts][www/macports] — Package manager                           | [BSD] (3-clause)
[![github]][github/swift]    [Swift][www/swift] — Programming language                            | [Apache] (2.0)
[![trac]][trac/webkit]       [WebKit][www/webkit] — Browser engine | [LGPL] (2.1)<br>[BSD] (2-clause)
[![github]][github/xnu]      [XNU][www/xnu] — Darwin kernel                                       | [APSL] (2.0)
[![github]][github/xorg-server] [XQuartz][www/xquartz] display server and<br>[![github]][github/quartz-wm] Window manager | [BSD], [MIT], [variants]<br>[APSL] (2.0)

[github/alac]: <https://github.com/macosforge/alac> "GitHub: macosforge/alac"
[www/alac]: <https://macosforge.github.io/alac/> "WWW: Apple Lossless Audio Codec"

[source/bonjour]: <https://opensource.apple.com/source/mDNSResponder/> "Source: mDNSResponder"
[www/bonjour]: <https://developer.apple.com/bonjour/> "WWW: Bonjour"

[github/cups]: <https://github.com/apple/cups> "GitHub: apple/cups"
[www/cups]: <https://www.cups.org/> "WWW: CUPS"

[source/darwin]: <https://opensource.apple.com/source/> "Source: Darwin"
[www/darwin]: <https://opensource.apple.com/> "WWW: Darwin"

[github/macports]: <https://github.com/macports/macports-base> "GitHub: macports/macports-base"
[www/macports]: <https://www.macports.org/> "WWW: MacPorts"

[github/swift]: <https://github.com/apple/swift> "GitHub: apple/swift"
[www/swift]: <https://swift.org/> "WWW: Swift"

[trac/webkit]: <https://trac.webkit.org/browser> "Trac: WebKit"
[www/webkit]: <https://webkit.org/> "WWW: WebKit"

[github/xnu]: <https://github.com/apple/darwin-xnu> "GitHub: apple/darwin-xnu"
[www/xnu]: <https://opensource.apple.com/source/xnu/> "WWW: XNU"

[github/xorg-server]: <https://github.com/XQuartz/xorg-server> "GitHub: XQuartz/xorg-server"
[github/quartz-wm]: <https://github.com/XQuartz/quartz-wm> "GitHub: XQuartz/quartz-wm"
[www/xquartz]: <https://www.xquartz.org/> "WWW:XQuartz"

Most of those licenses are [permissive] (which I favor), and I don't even have a problem with Tivoization *per se* — in other words, if I don't like that a particular hardware is restricted to a particular software, then I simply won't buy that hardware.  But when it comes to *personal computers* (and maybe even *smartphones*), one of my expectations is the freedom to choose what software I use on that computer.  In other words, for a general purpose computer with a given CPU architecture, I should be free to run any operating system I choose (for which I have obtained a valid license) that can be built for that architecture.  (Assuming, of course, availability of device drivers for that operating system.)  So if Tivoization is in the future for Macs, it would be a real disappointment, and I predict that Apple's sales would begin to drop as developers abandon macOS and switch to Linux (or even Windows) — and if developers aren't writing apps for macOS, it could even mean a drop in market-share overall as end-users abandon it too.


#### ...But I digress.

So if we have to switch to a different shell anyway, then why not try one in JavaScript, especially with its growing popularity for application development, not to mention its ubiquitous use on the Web?

Fortunately, [![github] Matt Daemon][github/matt-daemon] (April 2012) has already been developed.  This is not to be confused with later Matt Daemons, such as:

- [![github]][github/mattd.core] [![pypi]][pypi/mattd.core] mattd.core — Matt Daemon (August 2012):
  - A Python voice-to-text driven plugin system.

- [![github]][github/mattd] mattd — Matt Daemon (2013):
  - Forked from mattd.core.
  - `$ service mattd status`
    - Matt Daemon is running.
  - `$ service mattd stop`
    - You can't stop Matt Daemon. Permission denied. [FAILED]

- [![github]][github/matt-daemon (2)] [![npm]][npm/matt-daemon (2)] matt-daemon (2017):
  - An (apperently-actually-functional) Node.js HTTP daemon for serving static pages.
  - "With Matt Daemon, there are no surprises. He just serves."

- [![github]][github/matt-daemon (3)] [![pypi]][pypi/matt-daemon (3)] matt-daemon (2019):
  - A Python implementation of the Node.js matt-daemon HTTP daemon.

The original Matt Daemon was forked and developed into the [![github] Jason Bourne shell][github/jason-bourne-shell], which was itself forked and developed into the [![github] JSON Bourne shell][github/json-bourne-shell].  Unfortunately, the source code for these shells is currently published without a license, and therefore may not be used by anyone other than their respective copyright holders.

This situation might be similar to that of the original [Bourne shell][sh], whose copyright may be [disputed] as part of [Unix].  This perhaps contributed to the development of the [Bourne Again shell][bash] as an open-source replacement under [GNU].  Similarly, we have developed the [JSON Bourne Again shell][jsonbash] to provide a licensed alternative to the earlier Jason Bourne shell and JSON Bourne shell.


[github/matt-daemon]: <https://github.com/searls/matt-daemon> "GitHub: searls/matt-daemon"

[github/mattd.core]: <https://github.com/ralphbean/mattd.core> "GitHub: ralphbean/mattd.core"
[pypi/mattd.core]: <https://pypi.org/project/mattd.core/> "PyPI: mattd.core"

[github/mattd]: <https://github.com/mattray/mattd> "GitHub: mattray/mattd"

[github/matt-daemon (2)]: <https://github.com/innerdaze/matt-daemon> "GitHub: innerdaze/matt-daemon"
[npm/matt-daemon (2)]: <https://www.npmjs.com/package/matt-daemon> "npm: matt-daemon"

[github/matt-daemon (3)]: <https://github.com/k3rn31p4nic/matt-daemon> "GitHub: k3rn31p4nic/matt-daemon"
[pypi/matt-daemon (3)]: <https://pypi.org/project/matt-daemon/> "PyPI: matt-daemon"

[github/jason-bourne-shell]: <https://github.com/bostonaholic/jason-bourne-shell> "GitHub: bostonaholic/jason-bourne-shell"

[github/json-bourne-shell]: <https://github.com/Breton/json-bourne-shell> "GitHub: Breton/json-bourne-shell"


[Apple]: <https://en.wikipedia.org/wiki/Apple_Inc.> "Wikipedia: Apple Inc."
[macOS]: <https://en.wikipedia.org/wiki/MacOS> "Wikipedia: MacOS"
[Catalina]: <https://en.wikipedia.org/wiki/MacOS_Catalina> "Wikipedia: MacOS Catalina"
[shell]: <https://en.wikipedia.org/wiki/Shell_(computing)> "Wikipedia: Shell (computing)"
[switching]: <https://support.apple.com/HT208050> "Apple Support: Use zsh as the default shell on your Mac"
[licensing]: <https://thenextweb.com/dd/2019/06/04/why-does-macos-catalina-use-zsh-instead-of-bash-licensing/> "Why does macOS Catalina use Zsh instead of Bash? Licensing"
[GPL]: <https://en.wikipedia.org/wiki/GNU_General_Public_License> "Wikipedia: GNU General Public License"
[GPLv2]: <https://en.wikipedia.org/wiki/GNU_General_Public_License#Version_2> "Wikipedia: GNU General Public License#Version 2"
[GPLv3]: <https://en.wikipedia.org/wiki/GNU_General_Public_License#Version_3> "Wikipedia: GNU General Public License#Version 3"
[LGPL]: <https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License> "Wikipedia: GNU Lesser General Public License"
[Apache]: <https://en.wikipedia.org/wiki/Apache_License> "Wikipedia: Apache License"
[APSL]: <https://en.wikipedia.org/wiki/Apple_Public_Source_License> "Wikipedia: Apple Public Source License"
[BSD]: <https://en.wikipedia.org/wiki/BSD_licenses> "Wikipedia: BSD licenses"
[MIT]: <https://en.wikipedia.org/wiki/MIT_License> "Wikipedia: MIT License"
[variants]: <https://fedoraproject.org/wiki/Licensing:MIT> "Fedora Project: Licensing: MIT"
[copyleft]: <https://en.wikipedia.org/wiki/Copyleft> "Wikipedia: Copyleft"
[permissive]: <https://en.wikipedia.org/wiki/Permissive_software_license> "Wikipedia: Permissive software license"
[open-source software]: <https://en.wikipedia.org/wiki/Open-source_software> "Wikipedia: Open-source software"
[proprietary software]: <https://en.wikipedia.org/wiki/Proprietary_software> "Wikipedia: Proprietary software"
[hardware restriction]: <https://en.wikipedia.org/wiki/Hardware_restriction> "Wikipedia: Hardware restriction"
[Tivoization]: <https://en.wikipedia.org/wiki/Tivoization> "Wikipedia: Tivoization"
[TiVo]: <https://en.wikipedia.org/wiki/TiVo> "Wikipedia: TiVo"
[macOS forge]: <https://www.macosforge.org/> "macOS forge"
[disputed]: <https://en.wikipedia.org/wiki/SCO%E2%80%93Linux_disputes#UNIX_copyrights_ownership> "Wikipedia: SCO-Linux disputes#UNIX copyrights ownership"
[Unix]: <https://en.wikipedia.org/wiki/Unix> "Wikipedia: Unix"
[GNU]: <https://en.wikipedia.org/wiki/GNU> "Wikipedia: GNU"


### What about other shells for scripting/programming languages?

Perhaps similar to [csh]/[tcsh] for [C]...

- [C#]:
  - `cssh`?
  - `csharp`: https://www.mono-project.com/docs/tools+libraries/tools/repl/
  - `scriptcs`: https://github.com/scriptcs/scriptcs
  - `dotnet-script`: https://github.com/filipw/dotnet-script
  - `Nake`: https://github.com/yevhen/Nake
  - `csi`: https://docs.microsoft.com/en-us/archive/msdn-magazine/2016/january/essential-net-csharp-scripting

- [Lua]:
  - `luash`?
  - `#!/usr/bin/env lua`
  - `lua`: https://www.lua.org/manual/5.3/manual.html#7

- [Perl]:
  - `plsh`?
  - `#!/usr/bin/env perl`
  - `perl -de1`: https://perldoc.perl.org/perl.html

- [PHP]:
  - `phpsh`?
  - `#!/usr/bin/env php`
  - `php -a`: https://www.php.net/manual/en/features.commandline.interactive.php

- [PowerShell]:
  - `pwsh`?
  - `#!/usr/bin/env pwsh`
  - `pwsh`: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pwsh

- [Python]:
  - `pysh`?
  - `#!/usr/bin/env python3`
  - `python3`: https://docs.python.org/3/tutorial/interpreter.html

- [Ruby]:
  - `rbsh`?
  - `#!/usr/bin/env ruby`
  - `irb`: https://docs.ruby-lang.org/en/2.7.0/IRB.html

- [Scheme]:
  - `scsh`?
  - `#!/usr/bin/env mit-scheme`
  - `mit-scheme`: https://www.gnu.org/software/mit-scheme/documentation/mit-scheme-user/Basics-of-Starting-Scheme.html#Basics-of-Starting-Scheme
  - Or [`scsh`][scsh]?
  - `#!/usr/bin/scsh -s`
  - `!#`
  - `scsh`: https://scsh.net/docu/html/man-Z-H-12.html#node_chap_11

- [Swift]:
  - `swsh`?
  - `#!/usr/bin/env swift"
  - `swift`: https://developer.apple.com/swift/blog/?id=18

- [Tcl]/[Tk]:
  - `tclsh`?
  - `#!/usr/bin/env tclsh`
  - `tclsh`: https://www.tcl.tk/man/tcl8.6/UserCmd/tclsh.htm
  - Or [`wish`][wish]?
  - `#!/usr/bin/env wish`
  - `wish`: https://www.tcl.tk/man/tcl8.6/UserCmd/wish.htm
  - https://www.tcl.tk/man/tcl8.5/tutorial/Tcl0a.html


[C]: <https://en.wikipedia.org/wiki/C_(programming_language)> "Wikipedia: C (programming language)"
[C#]: <https://en.wikipedia.org/wiki/C_Sharp_(programming_language)> "Wikipedia: C Sharp (programming language)"
[Lua]: <https://en.wikipedia.org/wiki/Lua_(programming_language)> "Wikipedia: Lua (programming language)"
[Perl]: <https://en.wikipedia.org/wiki/Perl> "Wikipedia: Perl"
[PHP]: <https://en.wikipedia.org/wiki/PHP> "Wikipedia: PHP"
[PowerShell]: <https://en.wikipedia.org/wiki/PowerShell> "Wikipedia: PowerShell"
[Python]: <https://en.wikipedia.org/wiki/Python_(programming_language)> "Wikipedia: Python (programming language)"
[Ruby]: <https://en.wikipedia.org/wiki/Ruby_(programming_language)> "Wikipedia: Ruby (programming language)"
[Scheme]: <https://en.wikipedia.org/wiki/Scheme_(programming_language)> "Wikipedia: Scheme (programming language)"
[Swift]: <https://en.wikipedia.org/wiki/Swift_(programming_language)> "Wikipedia: Swift (programming language)"
[Tcl]: <https://en.wikipedia.org/wiki/Tcl> "Wikipedia: Tcl"
[Tk]: <https://en.wikipedia.org/wiki/Tk_(software)> "Wikipedia: Tk (software)"

[csh]: <https://en.wikipedia.org/wiki/C_shell> "Wikipedia: C shell"
[scsh]: <https://en.wikipedia.org/wiki/Scsh> "Wikipedia: Scsh"
[tcsh]: <https://en.wikipedia.org/wiki/Tcsh> "Wikipedia: Tcsh"
[wish]: <https://en.wikipedia.org/wiki/Wish_(Unix_shell)> "Wikipedia: Wish (Unix shell)"


---

## Unrelated but probably more useful things:

### Using shell commands in Node.js:

- [![github]][github/jBash] [![npm]][npm/jbash] [![www]][www/jbash] **jBash**: Implements some bash-like commands for use in JavaScript.

- [![github]][github/shelljs] [![wiki]][wiki/shelljs] [![npm]][npm/shelljs] [![www]][www/shelljs] **ShellJS**: Implements some bash commands for use in JavaScript.

  - [![github]][github/shx] [![npm]][npm/shx] **shx**: Run [ShellJS][github/shelljs] commands directly on the command line.

- [![github]][github/node-powershell] [![npm]][npm/node-powershell] [![www]][www/node-powershell] **Node-PowerShell**: Implements some PowerShell commands for use in JavaScript.

- [![github]][github/node-cmd] [![npm]][npm/node-cmd] **node-cmd**: Execute any existing shell commands in JavaScript.

[github/jBash]: <https://github.com/bradymholt/jBash> "GitHub: bradymholt/jBash"
[npm/jbash]: <https://www.npmjs.com/package/jbash> "npm: jbash"
[www/jbash]: <https://www.geekytidbits.com/jbash/> "WWW: jBash"

[github/shelljs]: <https://github.com/shelljs/shelljs> "GitHub: shelljs/shelljs"
[wiki/shelljs]: <https://github.com/shelljs/shelljs/wiki> "GitHub Wiki: shelljs/shelljs"
[npm/shelljs]: <https://www.npmjs.com/package/shelljs> "npm: shelljs"
[www/shelljs]: <https://documentup.com/shelljs/shelljs> "WWW: shelljs"

[github/shx]: <https://github.com/shelljs/shx> "GitHub: shelljs/shx"
[npm/shx]: <https://www.npmjs.com/package/shx> "npm: shx"

[github/node-powershell]: <https://github.com/rannn505/node-powershell> "GitHub: rannn505/node-powershell"
[npm/node-powershell]: <https://www.npmjs.com/package/node-powershell> "npm: node-powershell"
[www/node-powershell]: <https://rannn505.github.io/node-powershell/> "WWW: Node-PowerShell"

[github/node-cmd]: <https://github.com/RIAEvangelist/node-cmd> "GitHub: RIAEvangelist/node-cmd"
[npm/node-cmd]: <https://www.npmjs.com/package/node-cmd> "npm: node-cmd"


### Interactive shells:

- [![github]][github/cash] [![wiki]][wiki/cash] [![npm]][npm/cash] **Cash**: Implements some bash commands in an interactive shell running on Node.js.  The commands can also be used in JavaScript scripts.  (Implemented using [Vorpal][github/vorpal].)

- [![github]][github/jssh] [![npm]][npm/jssh] **jssh — JavaScript Shell**: An interactive JavaScript shell that runs on Node.js.  Also supports bash commands via [ShellJS][github/shelljs].

- [![github]][github/jsbash] [![www]][www/jsbash] **jsbash**: A bash interpreter, implemented in JavaScript.

[github/cash]: <https://github.com/dthree/cash> "GitHub: dthree/cash"
[wiki/cash]: <https://github.com/dthree/cash/wiki> "GitHub Wiki: dthree/cash"
[npm/cash]: <https://www.npmjs.com/package/cash> "npm: cash"

[github/jssh]: <https://github.com/streamich/jssh> "GitHub: streamich/jssh"
[npm/jssh]: <https://www.npmjs.com/package/jssh> "npm: jssh"

[github/jsbash]: <https://github.com/hamaxx/jsbash> "GitHub: hamaxx/jsbash"
[www/jsbash]: <http://jsbash.hamax.si/> "WWW: jsbash"


### Node.js tools for building interactive CLI apps:

- [![github]][github/chalk] [![npm]][npm/chalk] **Chalk**: Shell text styling.

- [![github]][github/minimist] [![npm]][npm/minimist] **minimist**: Parses command line arguments and options.

- [![github]][github/yargs] [![wiki]][wiki/yargs] [![npm]][npm/yargs] [![www]][www/yargs] **yargs**: Parses command line arguments and options; also provides a help system and command completion.  &#x2620;

- [![github]][github/commander.js] [![wiki]][wiki/commander.js] [![npm]][npm/commander.js] **commander.js**: Enables you to define the arguments and JavaScript code for a CLI command; when the command is run, commander.js parses the arguments and executes the code.

- [![github]][github/inquirer.js] [![wiki]][wiki/inquirer.js] [![npm]][npm/inquirer.js] **Inquirer.js**: Provides an interactive CLI by enabling you to implement prompts to the user.

- [![github]][github/vorpal] [![wiki]][wiki/vorpal] [![npm]][npm/vorpal] [![www]][www/vorpal] **Vorpal**: Based on [commander.js][github/commander.js], it uses [chalk][github/chalk] for styling, [minimist][github/minimist] for argument parsing, [Inquirer.js][github/inquirer.js] for interactive prompts, and implements its own help system and command completion to provide a complete interactive CLI app package.  [🗡️](<https://en.wikipedia.org/wiki/Jabberwocky>)

[github/chalk]: <https://github.com/chalk/chalk> "GitHub: chalk/chalk"
[npm/chalk]: <https://www.npmjs.com/package/chalk> "npm: chalk"

[github/minimist]: <https://github.com/substack/minimist> "GitHub: substack/minimist"
[npm/minimist]: <https://www.npmjs.com/package/minimist> "npm: minimist"

[github/yargs]: <https://github.com/yargs/yargs> "GitHub: yargs/yargs"
[wiki/yargs]: <https://github.com/yargs/yargs/wiki> "GitHub Wiki: yargs/yargs"
[npm/yargs]: <https://www.npmjs.com/package/yargs> "npm: yargs"
[www/yargs]: <http://yargs.js.org/> "WWW: Yargs"

[github/commander.js]: <https://github.com/tj/commander.js> "GitHub: tj/commander.js"
[wiki/commander.js]: <https://github.com/tj/commander.js/wiki> "GitHub Wiki: tj/commander.js"
[npm/commander.js]: <https://www.npmjs.com/package/commander> "npm: commander"

[github/inquirer.js]: <https://github.com/SBoudrias/Inquirer.js> "GitHub: SBoudrias/Inquirer.js"
[wiki/inquirer.js]: <https://github.com/SBoudrias/Inquirer.js/wiki> "GitHub Wiki: SBoudrias/Inquirer.js"
[npm/inquirer.js]: <https://www.npmjs.com/package/inquirer> "npm: inquirer"

[github/vorpal]: <https://github.com/dthree/vorpal> "GitHub: dthree/vorpal"
[wiki/vorpal]: <https://github.com/dthree/vorpal/wiki> "GitHub Wiki: dthree/vorpal"
[npm/vorpal]: <https://www.npmjs.com/package/vorpal> "npm: vorpal"
[www/vorpal]: <http://vorpal.js.org/> "WWW: Vorpal"


### JSON tools:

- [![github]][github/json.sh (1)] **JSON.sh**: Parses JSON in [POSIX] shells.

- [![github]][github/json-bash] **json-bash — JSON for Bash**: Processes JSON data in [bash].

- [![github]][github/json.sh (2)] [![npm]][npm/json.sh (2)] **JSON.sh**: Parses JSON in various [Unix shells][Unix shell] based on the [Bourne shell][sh] ([ash], [bash], [dash] and [zsh]).

- [![github]][github/jsonsh] [![www]][www/jsonsh] **JSON Syntax Highlight & Format**: Online formatting and syntax-highlighting of JSON data (copied-and-pasted, or directly from a web-service URL).


[github/json.sh (1)]: <https://github.com/rcrowley/json.sh> "GitHub: rcrowley/json.sh"

[github/json-bash]: <https://github.com/ingydotnet/json-bash> "GitHub: ingydotnet/json-bash"

[github/json.sh (2)]: <https://github.com/dominictarr/JSON.sh> "GitHub: dominictarr/JSON.sh"
[npm/json.sh (2)]: <https://www.npmjs.com/package/JSON.sh> "npm: jsonh.sh"

[github/jsonsh]: <https://github.com/manifestinteractive/jsonsh> "GitHub: manifestinteractive/jsonsh"
[www/jsonsh]: <https://jsonsh.com/> "WWW: JSON Syntax Highlight & Format"


[POSIX]: <https://en.wikipedia.org/wiki/POSIX> "Wikipedia: POSIX"
[Unix shell]: <https://en.wikipedia.org/wiki/Unix_shell> "Wikipedia: Unix shell"
[sh]: <https://en.wikipedia.org/wiki/Bourne_shell> "Wikipedia: Bourne shell"
[ash]: <https://en.wikipedia.org/wiki/Almquist_shell> "Wikipedia: Almquist shell"
[bash]: <https://en.wikipedia.org/wiki/Bash_(Unix_shell)> "Wikipedia: Bash (Unix shell)"
[dash]: <https://en.wikipedia.org/wiki/Almquist_shell#dash:_Ubuntu,_Debian_and_POSIX_compliance_of_Linux_distributions> "Wikipedia: Almquist shell#dash: Ubuntu, Debian and POSIX compliance of Linux distributions"
[zsh]: <https://en.wikipedia.org/wiki/Z_shell> "Wikipedia: Z shell"


[github]: <https://user-images.githubusercontent.com/30203863/72025642-ae498080-3270-11ea-92e4-ab87507862d6.png> "GitHub Repository"
[trac]: <https://user-images.githubusercontent.com/30203863/72215648-8dea2200-350d-11ea-8165-b3b82470e7c4.png> "Trac Repository"
[wiki]: <https://user-images.githubusercontent.com/30203863/72034716-b2d06200-328d-11ea-800c-b2b91fbe6a07.png> "GitHub Wiki"
[npm]: <https://user-images.githubusercontent.com/30203863/72025145-1dbe7080-326f-11ea-90d4-a18ce8941579.png> "npm"
[pypi]: <https://user-images.githubusercontent.com/30203863/72218522-6a39d280-3533-11ea-995f-83fe17ee30c5.png> "PyPI"
[www]: <https://user-images.githubusercontent.com/30203863/72025848-58290d00-3271-11ea-9b61-be54729b24d4.png> "WWW"


## Credits

This idea was previously mentioned on
[Reddit/ProgrammerHumor](<https://www.reddit.com/r/ProgrammerHumor/comments/6yf7bx/json_bourne/> "Reddit: JSON Bourne")
by [u/lmalmen](<https://www.reddit.com/user/lmalmen/> "Reddit: u/lmalmen"),
and on
[Twitter](<https://twitter.com/scherzmut/status/1033640084426432512?s=20> "Twitter: @schersmut: JSON Bourne Again Shell ... just to give some very wrong ideas here.")
by [Hersmut (@scherzmut)](<https://twitter.com/scherzmut> "Twitter: Herzmut (@scherzmut)")
in response to a
[tweet](<https://twitter.com/unixsteve/status/1033491395607187457?s=20> "Twitter: @unixsteve: Thought this might amuse  @nixcraft")
by [Steve Parker (@unixsteve)](<https://twitter.com/unixsteve> "Twitter: Steve Parker (@unixsteve)").

<img src="https://user-images.githubusercontent.com/30203863/72018999-b00b4800-3260-11ea-810b-5093f745e7ad.png"
     alt="Matt Daemon in JSON Bourne Again Shell"
     title="Matt Daemon in JSON Bourne Again Shell"
     width="50%"
/>

(Image based on
[Tutorial to Native Node.js Modules with C++. Part 2 — Arrays, JSON and Callbacks](<https://medium.com/@muehler.v/tutorial-to-node-js-native-c-modules-part-2-arrays-json-and-callbacks-9b81f09874cd> "Medium: Tutorial to Native Node.js Modules with C++. Part 2 — Arrays, JSON and Callbacks")
by [Vincent Mühler](<https://medium.com/@muehler.v> "Medium: Vincent Mühler").)

## License

Copyright © 2020 [`jsonbash` authors and contributors](https://github.com/ChrisTollefson/jsonbash/commits).

Licensed under the [MIT License](https://opensource.org/licenses/MIT).
See [LICENSE.md](https://github.com/ChrisTollefson/jsonbash/blob/master/LICENSE.md).
