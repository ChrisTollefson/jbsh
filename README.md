<!-- SPDX-License-Identifier: MIT -->
<!--
  Copyright © 2020 jsonbash authors and contributors (https://github.com/ChrisTollefson/jsonbash/graphs/contributors).
  Licensed under the MIT License (https://opensource.org/licenses/MIT).
  See LICENSE.md (https://github.com/ChrisTollefson/jsonbash/blob/master/LICENSE.md).
-->


# jsonbash — The JSON Bourne Again Shell

**[`matt-daemon`][github/matt-daemon]** stars in **[`jsonbash`] — the JSON Bourne Again shell**.

<img src="https://user-images.githubusercontent.com/30203863/72018999-b00b4800-3260-11ea-810b-5093f745e7ad.png"
     alt="Matt Daemon in JSON Bourne Again Shell"
     title="Matt Daemon in JSON Bourne Again Shell"
     width="50%"
/>

(Image based on [this](<https://medium.com/@muehler.v/tutorial-to-node-js-native-c-modules-part-2-arrays-json-and-callbacks-9b81f09874cd> "Medium: Tutorial to Native Node.js Modules with C++. Part 2 — Arrays, JSON and Callbacks").)

## TOC

TODO


## Installation

TODO

> Linux ladies *love* installing `matt-daemon`...

```Shell
finger
mount
unzip
strip
touch
more
yes yes
```

## Usage

TODO


## FAQ

### So it's actually JavaScript, not JSON?

OK, you got me, it's not JSON (at least insofar as [JSON] isn't [JavaScript]).


### Then why is it called JSON Bourne Again Shell?

To quote from the original projects<sup>[[1]][[2]][[3]]</sup>:

> I'm not sure what the [jsonbash] project does yet, but I'm pretty excited about the name.

[1]: <https://github.com/searls/matt-daemon/blob/master/README.md>              "GitHub: searls/matt-daemon/README.md"
[2]: <https://github.com/bostonaholic/jason-bourne-shell/blob/master/README.md> "GitHub: bostonaholic/jason-bourne-shell/README.md"
[3]: <https://github.com/Breton/json-bourne-shell/blob/master/README.md>        "GitHub: Breton/json-bourne-shell/README.md"


### Wait — is this shell just the Node.js REPL?

Yeah.

```Shell
#!/usr/bin/env node
```


### Hasn't that been done before?

[Yep](<https://stackoverflow.com/questions/33850903/use-node-js-as-shell> "Stack Overflow: Use Node.js as Shell").


### So is JSON Bourne Again Shell basically useless?

AFAICT, yes.


### Then why do this?

Idunno, for fun I guess?

But it was prompted by [Apple] [switching](<https://support.apple.com/HT208050> "Apple Support: Use zsh as the default shell on your Mac") the default [shell] from [Bourne Again Shell][`bash`] (GNU Bash) to [Z shell][`zsh`] as of [macOS] [Catalina (10.15)][Catalina].

#### To go off on an opinionated tangent...

This change in macOS was perhaps due to the [licensing](<https://thenextweb.com/dd/2019/06/04/why-does-macos-catalina-use-zsh-instead-of-bash-licensing/> "The Next Web: Why does macOS Catalina use Zsh instead of Bash? Licensing") of GNU Bash: version 4 (2009) and later have been licensed under [GPLv3], whereas version 3 (2004) was licensed under [GPLv2].  One motivation behind version 3 of the [GPL] was to restrict [Tivoization], whereby vendors of hardware (e.g. [TiVo]) would incorporate copyleft-licensed [open-source software] into their products, but use [hardware restriction] (such as digital signatures) to prevent modified versions of that software from running on those products — arguably defeating the [copyleft] purpose of the license as far as that hardware is concerned.  Even though GNU Bash is already at version 5 (2019), macOS still ships with version 3.2.57 (2007), which was the last version of GNU Bash licensed under GPLv2.  So maybe Apple is gearing up to implement some kind of Tivoization for their own hardware products?  To do so, they couldn't include any GPLv3 code in macOS, which might explain why GNU Bash is stuck at 3.2.57.

But according to http://meta.ath0.com/2012/02/05/apples-great-gpl-purge/, Apple has been removing specifically GPL-licensed software packages as of [Mac OS X Leopard (10.5)][Leopard] (or earlier?):

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

[Leopard]:       <https://en.wikipedia.org/wiki/Mac_OS_X_Leopard>      "Wikipedia: Mac OS X Leopard"
[Snow Leopard]:  <https://en.wikipedia.org/wiki/Mac_OS_X_Snow_Leopard> "Wikipedia: Mac OS X Snow Leopard"
[Lion]:          <https://en.wikipedia.org/wiki/Mac_OS_X_Lion>         "Wikipedia: Mac OS X Lion"
[Mountain Lion]: <https://en.wikipedia.org/wiki/OS_X_Mountain_Lion>    "Wikipedia: OS X Mountain Lion"
[Mavericks]:     <https://en.wikipedia.org/wiki/OS_X_Mavericks>        "Wikipedia: OS X Mavericks"
[Yosemite]:      <https://en.wikipedia.org/wiki/OS_X_Yosemite>         "Wikipedia: OS X Yosemite"
[El Capitan]:    <https://en.wikipedia.org/wiki/OS_X_El_Capitan>       "Wikipedia: OS X El Capitan"
[Sierra]:        <https://en.wikipedia.org/wiki/MacOS_Sierra>          "Wikipedia: macOS Sierra"
[Catalina]:      <https://en.wikipedia.org/wiki/MacOS_Catalina>        "Wikipedia: macOS Catalina"

Maybe that's a coincidence and this is speculation, but the switch to Z shell as the default could foreshadow GNU Bash's eventual removal from macOS entirely.  It's bad enough that it's already a decade out-of-date, but IMHO, the complete loss of `bash` would be unfortunate for developers on macOS and for interoperability between operating systems generally.

---

To be fair, Apple doesn't seem to be backing away from open-source; on the contrary, they appear to embrace it, for example, as stated at https://developer.apple.com/opensource/:

> Open source software is at the heart of Apple platforms and developer tools, and Apple continues to contribute and release significant quantities of open source code.

And I concur, based on some of the open-source projects listed there, or previously hosted at [macOS forge](<https://www.macosforge.org/> "macOS forge"):

| Project | License |
|---------|---------|
[![github]][github/alac]     [ALAC][www/alac] — Apple Lossless Audio Codec                        | [Apache] (2.0)
[![www]][source/bonjour]     [Bonjour][www/bonjour] mDNSResponder — Zero-configuration networking | [Apache] (2.0)
[![github]][github/cups] [![wiki]][wiki/cups] [CUPS][www/cups] — Common UNIX Printing System      | [Apache] (2.0)
[![www]][source/darwin]      [Darwin][www/darwin] — macOS/iOS core operating system               | [APSL] and others
[![github]][github/macports] [MacPorts][www/macports] — Package manager                           | [BSD] (3-clause)
[![github]][github/swift]    [Swift][www/swift] — Programming language                            | [Apache] (2.0)
[![trac]][trac/webkit] [![github] <sub>mirror</sub>][github/webkit] [WebKit][www/webkit] — Browser engine | [LGPL] (2.1)<br>[BSD] (2-clause)
[![github] <sub>mirror</sub>][github/xnu] [XNU][www/xnu] — Darwin kernel                          | [APSL] (2.0)
[XQuartz][www/xquartz] — [![github]][github/xorg-server] Display server and<br>[![github]][github/quartz-wm] Window manager | [BSD], [MIT], [variants]<br>[APSL] (2.0)

[github/alac]:        <https://github.com/macosforge/alac>        "GitHub: macosforge/alac"
[github/cups]:        <https://github.com/apple/cups>             "GitHub: apple/cups"
[github/macports]:    <https://github.com/macports/macports-base> "GitHub: macports/macports-base"
[github/quartz-wm]:   <https://github.com/XQuartz/quartz-wm>      "GitHub: XQuartz/quartz-wm"
[github/swift]:       <https://github.com/apple/swift>            "GitHub: apple/swift"
[github/webkit]:      <https://github.com/WebKit/webkit>          "GitHub: WebKit/webkit"
[github/xnu]:         <https://github.com/apple/darwin-xnu>       "GitHub: apple/darwin-xnu"
[github/xorg-server]: <https://github.com/XQuartz/xorg-server>    "GitHub: XQuartz/xorg-server"

[wiki/cups]: <https://github.com/apple/cups/wiki> "GitHub Wiki: apple/cups"

[trac/webkit]: <https://trac.webkit.org/browser> "Trac: WebKit"

[source/bonjour]: <https://opensource.apple.com/source/mDNSResponder/> "Source: mDNSResponder"
[source/darwin]:  <https://opensource.apple.com/source/>               "Source: Darwin"

[www/alac]:     <https://macosforge.github.io/alac/>       "WWW: Apple Lossless Audio Codec"
[www/bonjour]:  <https://developer.apple.com/bonjour/>     "WWW: Bonjour"
[www/cups]:     <https://www.cups.org/>                    "WWW: CUPS"
[www/darwin]:   <https://opensource.apple.com/>            "WWW: Darwin"
[www/macports]: <https://www.macports.org/>                "WWW: MacPorts"
[www/swift]:    <https://swift.org/>                       "WWW: Swift"
[www/webkit]:   <https://webkit.org/>                      "WWW: WebKit"
[www/xnu]:      <https://opensource.apple.com/source/xnu/> "WWW: XNU"
[www/xquartz]:  <https://www.xquartz.org/>                 "WWW:XQuartz"

[variants]: <https://fedoraproject.org/wiki/Licensing:MIT> "Fedora Project: Licensing: MIT"


But most of those licenses are [permissive], which would permit Tivoization.  I generally favour permissive licenses, and I don't have a problem with Tivoization *per se* — in other words, if I don't like that a particular hardware is restricted to a particular software, then I simply won't buy that hardware.  But when it comes to *personal computers* (and maybe even *smartphones*), one of my expectations is the freedom to choose what software I use on that computer.  In other words, for a general purpose computer with a given CPU architecture, I should be free to run any operating system I choose (for which I have obtained a valid license) that can be built for that architecture.  (Assuming, of course, availability of device drivers for that operating system.)  So if Tivoization is in the future for Macs, it would be a real disappointment to me.


#### ...But I digress.

So if we have to switch to a different shell anyway, then why not try one in JavaScript, especially with its growing popularity for application development, not to mention its ubiquitous use on the Web?

Fortunately, [Matt Daemon][github/matt-daemon] (April 2012) has already been developed.  This is not to be confused with later Matt Daemons, such as:

- [![github]][github/mattd.core] [![pypi]][pypi/mattd.core] mattd.core — Matt Daemon (August 2012):
  - A voice-to-text driven plugin system in Python.

* [![github]][github/mattd] mattd — Matt Daemon (2013):
  * Forked from mattd.core.
  * > `$ service mattd status`
    >
    > <sample>Matt Daemon is running.</sample>
    >
    > `$ service mattd stop`
    >
    > <sample>You can't stop Matt Daemon. Permission denied. [FAILED]</sample>

+ [![github]][github/matt-daemon (2)] [![npm]][npm/matt-daemon (2)] matt-daemon (2017):
  + A Node.js HTTP daemon for serving static files from a directory.
  + > With Matt Daemon, there are no surprises. He just serves.

- [![github]][github/matt-daemon (3)] [![pypi]][pypi/matt-daemon (3)] matt-daemon (2019):
  - A Python HTTP daemon for serving static files from a directory.

The original Matt Daemon was forked and developed into the [Jason Bourne shell][github/jason-bourne-shell], which was itself forked and developed into the [JSON Bourne shell][github/json-bourne-shell].  Unfortunately, the source code for these projects is currently published without a license, and therefore may not be used by anyone other than their respective copyright holders, as mentioned in [GitHub Help](<https://help.github.com/en/github/creating-cloning-and-archiving-repositories/licensing-a-repository#choosing-the-right-license> "GitHub Help: Licensing a repository#Choosing the right license"):

> ...without a license, the default copyright laws apply, meaning that you retain all rights to your source code and no one may reproduce, distribute, or create derivative works from your work.

This situation might be similar to that of the original [Bourne shell][`sh`], whose copyright may be [disputed](<https://en.wikipedia.org/wiki/SCO%E2%80%93Linux_disputes#UNIX_copyrights_ownership> "Wikipedia: SCO-Linux disputes#UNIX copyrights ownership") as part of [Unix].  This perhaps contributed to the development of the [Bourne Again shell][`bash`] as an open-source replacement under [GNU].  Similarly, we have developed the [JSON Bourne Again shell][`jsonbash`] to provide a licensed alternative to the Jason Bourne shell and JSON Bourne shell (and Matt Daemon) via a complete re-write, so that none of the unlicensed code remains.


### What about shells for other scripting/programming languages?

...Perhaps along the lines of [`csh`]/[`tcsh`] for [C].

```Shell
#!/usr/bin/env ____
```

- [C#]:
  - `csharp`: https://www.mono-project.com/docs/tools+libraries/tools/repl/
  - `scriptcs` (2018): https://github.com/scriptcs/scriptcs
  - `dotnet-script`: https://github.com/filipw/dotnet-script
  - `Nake` (2017): https://github.com/yevhen/Nake
  - `csi`: https://docs.microsoft.com/en-us/archive/msdn-magazine/2016/january/essential-net-csharp-scripting

+ [Java]:
  + `jshell`: https://docs.oracle.com/en/java/javase/13/jshell/introduction-jshell.html

* [JavaScript]:
  * [V8] ([Chromium]):
    * `node`: https://nodejs.org/en/docs/guides/debugging-getting-started/#command-line-options
  * [SpiderMonkey] ([Mozilla]):
    * `js`: https://developer.mozilla.org/en-US/docs/Mozilla/Projects/SpiderMonkey/Introduction_to_the_JavaScript_shell
    * `jsdb` (2012): http://www.jsdb.org/
    * `jls` (2017): http://javalikescript.free.fr/

- [Lisp]:
  - `sbcl`: http://www.sbcl.org/getting.html

+ [Lua]:
  + `lua`: https://www.lua.org/manual/5.3/manual.html#7

* [Perl]:
  * `perl -de1`: https://perldoc.perl.org/perl.html
  * `psh` (2007): https://metacpan.org/pod/distribution/psh/doc/psh.pod

- [PHP]:
  - `php -a`: https://www.php.net/manual/en/features.commandline.interactive.php

+ [PowerShell]:
  + `pwsh`: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pwsh

* [Python]:
  * `python3`: https://docs.python.org/3/tutorial/interpreter.html

- [Ruby]:
  - `irb`: https://docs.ruby-lang.org/en/2.7.0/IRB.html

+ [Scheme]:
  + [`scsh`] (2006): https://scsh.net/docu/html/man-Z-H-12.html#node_chap_11
  + `mit-scheme`: https://www.gnu.org/software/mit-scheme/documentation/mit-scheme-user/Basics-of-Starting-Scheme.html#Basics-of-Starting-Scheme

* [Swift]:
  * `swift`: https://developer.apple.com/swift/blog/?id=18

- [Tcl]/[Tk]:
  - `tclsh`: https://www.tcl.tk/man/tcl8.6/UserCmd/tclsh.htm
  - [`wish`][`wish`]: https://www.tcl.tk/man/tcl8.6/UserCmd/wish.htm


## Other things with similar names — and things related to those things — none of which are related to jsonbash:

### Using shell commands in Node.js:

- [![github]][github/jBash] [![npm]][npm/jbash] [![www]][www/jbash] **jBash**: Implements some `bash`-like commands for use in JavaScript.

+ [![github]][github/shelljs] [![wiki]][wiki/shelljs] [![npm]][npm/shelljs] [![www]][www/shelljs] **ShellJS**: Implements some `bash` commands for use in JavaScript.
  + [![github]][github/shx] [![npm]][npm/shx] **shx**: Run [ShellJS][github/shelljs] commands directly on the command line.

* [![github]][github/node-powershell] [![npm]][npm/node-powershell] [![www]][www/node-powershell] **Node-PowerShell**: Implements some PowerShell commands for use in JavaScript.

- [![github]][github/node-cmd] [![npm]][npm/node-cmd] **node-cmd**: Execute any existing shell commands in JavaScript.


### Interactive shells:

- [![github]][github/cash] [![wiki]][wiki/cash] [![npm]][npm/cash] **Cash**: Implements some `bash` commands in an interactive shell running on Node.js.  The commands can also be used in JavaScript scripts.  (Implemented using [Vorpal][github/vorpal].)

- [![github]][github/jssh] [![npm]][npm/jssh] **jssh — JavaScript Shell**: An interactive JavaScript shell that runs on Node.js.  Also supports `bash` commands via [ShellJS][github/shelljs].

- [![github]][github/jsbash] [![www]][www/jsbash] **jsbash**: A `bash` interpreter, implemented in JavaScript.


### Node.js tools for building interactive CLI apps:

- [![github]][github/chalk] [![npm]][npm/chalk] **Chalk**: Shell text styling.

- [![github]][github/minimist] [![npm]][npm/minimist] **minimist**: Parses command line arguments and options.

- [![github]][github/yargs] [![wiki]][wiki/yargs] [![npm]][npm/yargs] [![www]][www/yargs] **yargs**: Parses command line arguments and options; also provides a help system and command completion.  &#x2620;

- [![github]][github/commander.js] [![wiki]][wiki/commander.js] [![npm]][npm/commander.js] **commander.js**: Enables you to define the arguments and JavaScript code for a CLI command; when the command is run, commander.js parses the arguments and executes the code.

- [![github]][github/inquirer.js] [![wiki]][wiki/inquirer.js] [![npm]][npm/inquirer.js] **Inquirer.js**: Provides an interactive CLI by enabling you to implement prompts to the user.

- [![github]][github/vorpal] [![wiki]][wiki/vorpal] [![npm]][npm/vorpal] [![www]][www/vorpal] **Vorpal**: Based on [commander.js][github/commander.js], it uses [chalk][github/chalk] for styling, [minimist][github/minimist] for argument parsing, [Inquirer.js][github/inquirer.js] for interactive prompts, and implements its own help system and command completion to provide a complete interactive CLI app package (e.g. [Cash][github/cash]).  [🗡️](<https://en.wikipedia.org/wiki/Jabberwocky>)


### JSON tools:

- [![github]][github/json.sh (1)] **JSON.sh**: Parses JSON in [POSIX] shells.

- [![github]][github/json-bash] **json-bash — JSON for Bash**: Processes JSON data in [`bash`].

- [![github]][github/json.sh (2)] [![npm]][npm/json.sh (2)] **JSON.sh**: Parses JSON in various [Unix shells][Unix shell] based on the [Bourne shell][`sh`] ([`ash`], [`bash`], [`dash`] and [`zsh`]).

- [![github]][github/jsonsh] [![www]][www/jsonsh] **[jsonsh.com][www/jsonsh] — JSON Syntax Highlight & Format**: Online formatting and syntax-highlighting of JSON data (copied-and-pasted, or directly from a web-service URL).

## Other tools/info:

### Node.js:

- [![github]][github/node] [![npm]][npm/node] [![www]][www/node] **`node`** — Node.js.
- [![github]][github/npm] [![wiki]][wiki/npm] [![npm]][npm/npm] [![www]][www/npm]  **`npm`**   — Node Package Manager.
- [![github]][github/yarn] [![npm]][npm/yarn] [![www]][www/yarn] **`yarn`** — Node.js package manager (using npm repository) from Facebook.
- [![github]][github/n] [![wiki]][wiki/n] [![npm]][npm/n] **`n`** — Node.js version manager.
- [![github]][github/nvm] **`nvm`** — Node Version Manager.
- [![github]][github/nvs] **`nvs`** — Node Version Switcher.

### Browser/JavaScript engines:

- [Blink] (forked from WebCore)/[V8] ([Google]):
  - [Chromium], [Chrome], [Edge] (soon - in beta), [Opera], [Node.js], [Android] browsers.

+ [EdgeHTML]/[Chakra] ([Microsoft]):
  + [Edge] (for now).

* [Gecko, Quantum][Gecko]/[SpiderMonkey] ([Mozilla]):
  * [Firefox] and derivatives.

- [WebKit] — WebCore/JavaScriptCore ([Apple]):
  - [Safari], [iOS] browsers.


## Credits

- [![github]][github/matt-daemon] **matt-daemon** — Matt Daemon (April 2012)
- [![github]][github/mattd.core] [![pypi]][pypi/mattd.core] **mattd.core** — Matt Daemon (August 2012)
- [![github]][github/mattd] **mattd** — Matt Daemon (2013)
- [![github]][github/matt-daemon (2)] [![npm]][npm/matt-daemon (2)] **matt-daemon** — Matt Daemon (2017)
- [![github]][github/matt-daemon (3)] [![pypi]][pypi/matt-daemon (3)] **matt-daemon** — Matt Daemon (2019)
- [![github]][github/jason-bourne-shell] **jason-bourne-shell** — Jason Bourne shell (2016)
- [![github]][github/json-bourne-shell] **json-bourne-shell** — JSON Bourne shell (2017)
- [Reddit/ProgrammerHumor](<https://www.reddit.com/r/ProgrammerHumor/comments/6yf7bx/json_bourne/> "Reddit: JSON Bourne") post by [u/lmalmen](<https://www.reddit.com/user/lmalmen/> "Reddit: u/lmalmen") (2017).
- [Tutorial to Native Node.js Modules with C++. Part 2 — Arrays, JSON and Callbacks](<https://medium.com/@muehler.v/tutorial-to-node-js-native-c-modules-part-2-arrays-json-and-callbacks-9b81f09874cd> "Medium: Tutorial to Native Node.js Modules with C++. Part 2 — Arrays, JSON and Callbacks") by [Vincent Mühler](<https://medium.com/@muehler.v> "Medium: Vincent Mühler") (2017).
- [Twitter comment](<https://twitter.com/scherzmut/status/1033640084426432512?s=20> "Twitter: @schersmut: JSON Bourne Again Shell ... just to give some very wrong ideas here.") by [Hersmut (@scherzmut)](<https://twitter.com/scherzmut> "Twitter: Herzmut (@scherzmut)") (2018).
  - [Tweet](<https://twitter.com/unixsteve/status/1033491395607187457?s=20> "Twitter: @unixsteve: Thought this might amuse  @nixcraft") by [Steve Parker (@unixsteve)](<https://twitter.com/unixsteve> "Twitter: Steve Parker (@unixsteve)") (2018).


<!-- Reference links: -->

[`jsonbash`]: <https://github.com/ChrisTollefson/jsonbash> "GitHub: ChrisTollefson/jsonbash"

<!-- Wikipedia reference links: -->

[copyleft]:             <https://en.wikipedia.org/wiki/Copyleft>                    "Wikipedia: Copyleft"
[hardware restriction]: <https://en.wikipedia.org/wiki/Hardware_restriction>        "Wikipedia: Hardware restriction"
[Node.js]:              <https://en.wikipedia.org/wiki/Node.js>                     "Wikipedia: Node.js"
[open-source software]: <https://en.wikipedia.org/wiki/Open-source_software>        "Wikipedia: Open-source software"
[permissive]:           <https://en.wikipedia.org/wiki/Permissive_software_license> "Wikipedia: Permissive software license"
[POSIX]:                <https://en.wikipedia.org/wiki/POSIX>                       "Wikipedia: POSIX"
[proprietary software]: <https://en.wikipedia.org/wiki/Proprietary_software>        "Wikipedia: Proprietary software"
[shell]:                <https://en.wikipedia.org/wiki/Shell_(computing)>           "Wikipedia: Shell (computing)"
[TiVo]:                 <https://en.wikipedia.org/wiki/TiVo>                        "Wikipedia: TiVo"
[Tivoization]:          <https://en.wikipedia.org/wiki/Tivoization>                 "Wikipedia: Tivoization"
[Tk]:                   <https://en.wikipedia.org/wiki/Tk_(software)>               "Wikipedia: Tk (software)"
[Unix shell]:           <https://en.wikipedia.org/wiki/Unix_shell>                  "Wikipedia: Unix shell"

<!-- Wikipedia reference links - software licenses: -->

[Apache]: <https://en.wikipedia.org/wiki/Apache_License>                    "Wikipedia: Apache License"
[APSL]:   <https://en.wikipedia.org/wiki/Apple_Public_Source_License>       "Wikipedia: Apple Public Source License"
[BSD]:    <https://en.wikipedia.org/wiki/BSD_licenses>                      "Wikipedia: BSD licenses"
[GPL]:    <https://en.wikipedia.org/wiki/GNU_General_Public_License>        "Wikipedia: GNU General Public License"
[GPLv2]:  <https://en.wikipedia.org/wiki/GNU_General_Public_License#Version_2> "Wikipedia: GNU General Public License#Version 2"
[GPLv3]:  <https://en.wikipedia.org/wiki/GNU_General_Public_License#Version_3> "Wikipedia: GNU General Public License#Version 3"
[LGPL]:   <https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License> "Wikipedia: GNU Lesser General Public License"
[MIT]:    <https://en.wikipedia.org/wiki/MIT_License>                       "Wikipedia: MIT License"

<!-- Wikipedia reference links - programming languages: -->

[C]:          <https://en.wikipedia.org/wiki/C_(programming_language)>       "Wikipedia: C (programming language)"
[C#]:         <https://en.wikipedia.org/wiki/C_Sharp_(programming_language)> "Wikipedia: C Sharp (programming language)"
[Java]:       <https://en.wikipedia.org/wiki/Java_(programming_language)>    "Wikipedia: Java (programming language)"
[JavaScript]: <https://en.wikipedia.org/wiki/JavaScript>                     "Wikipedia: JavaScript"
[JSON]:       <https://en.wikipedia.org/wiki/JSON>                           "Wikipedia: JSON"
[Lisp]:       <https://en.wikipedia.org/wiki/Lisp_(programming_language)>    "Wikipedia: Lisp (programming language)"
[Lua]:        <https://en.wikipedia.org/wiki/Lua_(programming_language)>     "Wikipedia: Lua (programming language)"
[Perl]:       <https://en.wikipedia.org/wiki/Perl>                           "Wikipedia: Perl"
[PHP]:        <https://en.wikipedia.org/wiki/PHP>                            "Wikipedia: PHP"
[PowerShell]: <https://en.wikipedia.org/wiki/PowerShell>                     "Wikipedia: PowerShell"
[Python]:     <https://en.wikipedia.org/wiki/Python_(programming_language)>  "Wikipedia: Python (programming language)"
[REPL]: <https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop> "Wikipedia: Read-eval-print loop"
[Ruby]:       <https://en.wikipedia.org/wiki/Ruby_(programming_language)>    "Wikipedia: Ruby (programming language)"
[Scheme]:     <https://en.wikipedia.org/wiki/Scheme_(programming_language)>  "Wikipedia: Scheme (programming language)"
[Swift]:      <https://en.wikipedia.org/wiki/Swift_(programming_language)>   "Wikipedia: Swift (programming language)"
[Tcl]:        <https://en.wikipedia.org/wiki/Tcl>                            "Wikipedia: Tcl"

<!-- Wikipedia reference links - shells: -->

[`ash`]:  <https://en.wikipedia.org/wiki/Almquist_shell>    "Wikipedia: Almquist shell"
[`bash`]: <https://en.wikipedia.org/wiki/Bash_(Unix_shell)> "Wikipedia: Bash (Unix shell)"
[`csh`]:  <https://en.wikipedia.org/wiki/C_shell>           "Wikipedia: C shell"
[`dash`]: <https://en.wikipedia.org/wiki/Almquist_shell#dash:_Ubuntu,_Debian_and_POSIX_compliance_of_Linux_distributions> "Wikipedia: Almquist shell#dash: Ubuntu, Debian and POSIX compliance of Linux distributions"
[`scsh`]: <https://en.wikipedia.org/wiki/Scsh>              "Wikipedia: Scsh"
[`sh`]:   <https://en.wikipedia.org/wiki/Bourne_shell>      "Wikipedia: Bourne shell"
[`tcsh`]: <https://en.wikipedia.org/wiki/Tcsh>              "Wikipedia: Tcsh"
[`wish`]: <https://en.wikipedia.org/wiki/Wish_(Unix_shell)> "Wikipedia: Wish (Unix shell)"
[`zsh`]:  <https://en.wikipedia.org/wiki/Z_shell>           "Wikipedia: Z shell"

<!-- Wikipedia reference links - browser engines: -->

[Blink]:    <https://en.wikipedia.org/wiki/Blink_(browser_engine)> "Wikipedia: Blink (browser engine)"
[EdgeHTML]: <https://en.wikipedia.org/wiki/EdgeHTML>               "Wikipedia: EdgeHTML"
[Gecko]:    <https://en.wikipedia.org/wiki/Gecko_(software)>       "Wikipedia: Gecko (software)"
[WebKit]:   <https://en.wikipedia.org/wiki/WebKit>                 "Wikipedia: WebKit"

<!-- Wikipedia reference links: JavaScript engines: -->

[Chakra]:       <https://en.wikipedia.org/wiki/Chakra_(JavaScript_engine)> "Wikipedia: Chakra (JavaScript engine)"
[SpiderMonkey]: <https://en.wikipedia.org/wiki/SpiderMonkey>               "Wikipedia: SpiderMonkey"
[V8]:           <https://en.wikipedia.org/wiki/V8_(JavaScript_engine)>     "Wikipedia: V8 (JavaScript engine)"

<!-- Wikipedia reference links: web browsers: -->

[Chrome]:   <https://en.wikipedia.org/wiki/Google_Chrome>          "Wikipedia: Google Chrome"
[Chromium]: <https://en.wikipedia.org/wiki/Chromium_(web_browser)> "Wikipedia: Chromium (web browser"
[Edge]:     <https://en.wikipedia.org/wiki/Microsoft_Edge>         "Wikipedia: Microsoft Edge"
[Firefox]:  <https://en.wikipedia.org/wiki/Firefox>                "Wikipedia: Firefox"
[Opera]:    <https://en.wikipedia.org/wiki/Opera_(web_browser)>    "Wikipedia: Opera (web browser)"
[Safari]:   <https://en.wikipedia.org/wiki/Safari_(web_browser)>   "Wikipedia: Safari (web browser)"

<!-- Wikipedia reference links: operating systems: -->

[Android]: <https://en.wikipedia.org/wiki/Android_(operating_system)> "Wikipedia: Android (operating system)"
[GNU]:     <https://en.wikipedia.org/wiki/GNU>                        "Wikipedia: GNU"
[iOS]:     <https://en.wikipedia.org/wiki/IOS>                        "Wikipedia: iOS"
[macOS]:   <https://en.wikipedia.org/wiki/MacOS>                      "Wikipedia: macOS"
[Unix]:    <https://en.wikipedia.org/wiki/Unix>                       "Wikipedia: Unix"

<!-- Wikipedia reference links: organizations: -->

[Apple]:     <https://en.wikipedia.org/wiki/Apple_Inc.>         "Wikipedia: Apple Inc."
[Google]:    <https://en.wikipedia.org/wiki/Google>             "Wikipedia: Google"
[Microsoft]: <https://en.wikipedia.org/wiki/Microsoft>          "Wikipedia: Microsoft"
[Mozilla]:   <https://en.wikipedia.org/wiki/Mozilla_Foundation> "Wikipedia: Mozilla Foundation"

<!-- Websites: -->

[www/jbash]:           <https://www.geekytidbits.com/jbash/>         "WWW: jBash"
[www/jsbash]:          <http://jsbash.hamax.si/>                     "WWW: jsbash"
[www/jsonsh]:          <https://jsonsh.com/>                         "WWW: JSON Syntax Highlight & Format"
[www/node]:            <https://nodejs.org/>                         "WWW: Node.js"
[www/node-powershell]: <https://rannn505.github.io/node-powershell/> "WWW: Node-PowerShell"
[www/npm]:             <https://www.npmjs.com/>                      "WWW: NPM"
[www/shelljs]:         <https://documentup.com/shelljs/shelljs>      "WWW: shelljs"
[www/vorpal]:          <http://vorpal.js.org/>                       "WWW: Vorpal"
[www/yargs]:           <http://yargs.js.org/>                        "WWW: Yargs"
[www/yarn]:            <https://yarnpkg.com/>                        "WWW: Yarn"

<!-- GitHub repos: -->

[github/cash]:               <https://github.com/dthree/cash>                     "GitHub: dthree/cash"
[github/chalk]:              <https://github.com/chalk/chalk>                     "GitHub: chalk/chalk"
[github/commander.js]:       <https://github.com/tj/commander.js>                 "GitHub: tj/commander.js"
[github/inquirer.js]:        <https://github.com/SBoudrias/Inquirer.js>           "GitHub: SBoudrias/Inquirer.js"
[github/jason-bourne-shell]: <https://github.com/bostonaholic/jason-bourne-shell> "GitHub: bostonaholic/jason-bourne-shell"
[github/jBash]:              <https://github.com/bradymholt/jBash>                "GitHub: bradymholt/jBash"
[github/jsbash]:             <https://github.com/hamaxx/jsbash>                   "GitHub: hamaxx/jsbash"
[github/json.sh (1)]:        <https://github.com/rcrowley/json.sh>                "GitHub: rcrowley/json.sh"
[github/json.sh (2)]:        <https://github.com/dominictarr/JSON.sh>             "GitHub: dominictarr/JSON.sh"
[github/json-bash]:          <https://github.com/ingydotnet/json-bash>            "GitHub: ingydotnet/json-bash"
[github/json-bourne-shell]:  <https://github.com/Breton/json-bourne-shell>        "GitHub: Breton/json-bourne-shell"
[github/jsonsh]:             <https://github.com/manifestinteractive/jsonsh>      "GitHub: manifestinteractive/jsonsh"
[github/jssh]:               <https://github.com/streamich/jssh>                  "GitHub: streamich/jssh"
[github/matt-daemon]:        <https://github.com/searls/matt-daemon>              "GitHub: searls/matt-daemon"
[github/matt-daemon (2)]:    <https://github.com/innerdaze/matt-daemon>           "GitHub: innerdaze/matt-daemon"
[github/matt-daemon (3)]:    <https://github.com/k3rn31p4nic/matt-daemon>         "GitHub: k3rn31p4nic/matt-daemon"
[github/mattd]:              <https://github.com/mattray/mattd>                   "GitHub: mattray/mattd"
[github/mattd.core]:         <https://github.com/ralphbean/mattd.core>            "GitHub: ralphbean/mattd.core"
[github/minimist]:           <https://github.com/substack/minimist>               "GitHub: substack/minimist"
[github/n]:                  <https://github.com/tj/n>                            "GitHub: tj/n"
[github/node]:               <https://github.com/nodejs/node>                     "GitHub: nodejs/node"
[github/node-cmd]:           <https://github.com/RIAEvangelist/node-cmd>          "GitHub: RIAEvangelist/node-cmd"
[github/node-powershell]:    <https://github.com/rannn505/node-powershell>        "GitHub: rannn505/node-powershell"
[github/npm]:                <https://github.com/npm/cli>                         "GitHub: npm/cli"
[github/nvm]:                <https://github.com/nvm-sh/nvm>                      "GitHub: nvm-sh/nvm"
[github/nvs]:                <https://github.com/jasongin/nvs>                    "GitHub: jasongin/nvs"
[github/shelljs]:            <https://github.com/shelljs/shelljs>                 "GitHub: shelljs/shelljs"
[github/shx]:                <https://github.com/shelljs/shx>                     "GitHub: shelljs/shx"
[github/vorpal]:             <https://github.com/dthree/vorpal>                   "GitHub: dthree/vorpal"
[github/yargs]:              <https://github.com/yargs/yargs>                     "GitHub: yargs/yargs"
[github/yarn]:               <https://github.com/yarnpkg/yarn>                    "GitHub: yarnpkg/yarn"

<!-- GitHub repo wikis: -->

[wiki/cash]:         <https://github.com/dthree/cash/wiki>           "GitHub Wiki: dthree/cash"
[wiki/commander.js]: <https://github.com/tj/commander.js/wiki>       "GitHub Wiki: tj/commander.js"
[wiki/inquirer.js]:  <https://github.com/SBoudrias/Inquirer.js/wiki> "GitHub Wiki: SBoudrias/Inquirer.js"
[wiki/n]:            <https://github.com/tj/n/wiki>                  "GitHub Wiki: tj/n"
[wiki/npm]:          <https://github.com/npm/cli/wiki>               "GitHub Wiki: npm/cli"
[wiki/shelljs]:      <https://github.com/shelljs/shelljs/wiki>       "GitHub Wiki: shelljs/shelljs"
[wiki/vorpal]:       <https://github.com/dthree/vorpal/wiki>         "GitHub Wiki: dthree/vorpal"
[wiki/yargs]:        <https://github.com/yargs/yargs/wiki>           "GitHub Wiki: yargs/yargs"

<!-- npm repos: -->

[npm/cash]:            <https://www.npmjs.com/package/cash>            "npm: cash"
[npm/chalk]:           <https://www.npmjs.com/package/chalk>           "npm: chalk"
[npm/commander.js]:    <https://www.npmjs.com/package/commander>       "npm: commander"
[npm/inquirer.js]:     <https://www.npmjs.com/package/inquirer>        "npm: inquirer"
[npm/jbash]:           <https://www.npmjs.com/package/jbash>           "npm: jbash"
[npm/json.sh (2)]:     <https://www.npmjs.com/package/JSON.sh>         "npm: jsonh.sh"
[npm/jssh]:            <https://www.npmjs.com/package/jssh>            "npm: jssh"
[npm/matt-daemon (2)]: <https://www.npmjs.com/package/matt-daemon>     "npm: matt-daemon"
[npm/minimist]:        <https://www.npmjs.com/package/minimist>        "npm: minimist"
[npm/n]:               <https://www.npmjs.com/package/n>               "npm: n"
[npm/node]:            <https://www.npmjs.com/package/node>            "npm: node"
[npm/node-cmd]:        <https://www.npmjs.com/package/node-cmd>        "npm: node-cmd"
[npm/node-powershell]: <https://www.npmjs.com/package/node-powershell> "npm: node-powershell"
[npm/npm]:             <https://www.npmjs.com/package/npm>             "npm: npm"
[npm/shelljs]:         <https://www.npmjs.com/package/shelljs>         "npm: shelljs"
[npm/shx]:             <https://www.npmjs.com/package/shx>             "npm: shx"
[npm/vorpal]:          <https://www.npmjs.com/package/vorpal>          "npm: vorpal"
[npm/yargs]:           <https://www.npmjs.com/package/yargs>           "npm: yargs"
[npm/yarn]:            <https://www.npmjs.com/package/yarn>            "npm: yarn"

<!-- PyPI repos: -->

[pypi/mattd.core]:      <https://pypi.org/project/mattd.core/>  "PyPI: mattd.core"
[pypi/matt-daemon (3)]: <https://pypi.org/project/matt-daemon/> "PyPI: matt-daemon"

<!-- Icons: -->

[github]: <https://user-images.githubusercontent.com/30203863/72025642-ae498080-3270-11ea-92e4-ab87507862d6.png> "GitHub Repository"
[trac]:   <https://user-images.githubusercontent.com/30203863/72215648-8dea2200-350d-11ea-8165-b3b82470e7c4.png> "Trac Repository"
[wiki]:   <https://user-images.githubusercontent.com/30203863/72034716-b2d06200-328d-11ea-800c-b2b91fbe6a07.png> "GitHub Wiki"
[npm]:    <https://user-images.githubusercontent.com/30203863/72025145-1dbe7080-326f-11ea-90d4-a18ce8941579.png> "npm"
[pypi]:   <https://user-images.githubusercontent.com/30203863/72218522-6a39d280-3533-11ea-995f-83fe17ee30c5.png> "PyPI"
[www]:    <https://user-images.githubusercontent.com/30203863/72025848-58290d00-3271-11ea-9b61-be54729b24d4.png> "WWW"


## License

Licensed under the [MIT License](https://opensource.org/licenses/MIT).
See [LICENSE.md](https://github.com/ChrisTollefson/jsonbash/blob/master/LICENSE.md).

Copyright © 2020 [jsonbash authors and contributors](https://github.com/ChrisTollefson/jsonbash/graphs/contributors).
