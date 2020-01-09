# jsonbash — The JSON Bourne Again Shell

`jsonbash` is a JavaScript shell.


## So it's actually JavaScript, not JSON?

OK, you got me, it's not JSON (at least insofar as JSON isn't JavaScript).


## Then why is it *called JSON* Bourne Again Shell?

I'm not sure what the jsonbash project does yet, but I'm pretty excited about the name.


## Wait — is this shell just the Node.js REPL?

Yeah.


## Hasn't that been done before?

[Yes](<https://stackoverflow.com/questions/33850903/use-node-js-as-shell> "Stack Overflow: Use Node.js as Shell").


## So is `jsonbash` basically useless?

AFAICT, yes.


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


### Bash tools:

- [![github]][github/json-bash] **json-bash — JSON for Bash**: Enables processing of JSON data in bash.

[github/json-bash]: <https://github.com/ingydotnet/json-bash> "GitHub: ingydotnet/json-bash"


[github]: <https://user-images.githubusercontent.com/30203863/72025642-ae498080-3270-11ea-92e4-ab87507862d6.png> "GitHub Repository"
[wiki]: <https://user-images.githubusercontent.com/30203863/72034716-b2d06200-328d-11ea-800c-b2b91fbe6a07.png> "GitHub Wiki"
[npm]: <https://user-images.githubusercontent.com/30203863/72025145-1dbe7080-326f-11ea-90d4-a18ce8941579.png> "npm"
[www]: <https://user-images.githubusercontent.com/30203863/72025848-58290d00-3271-11ea-9b61-be54729b24d4.png> "WWW"


## This project is based upon:

- The [matt-daemon](<https://github.com/searls/matt-daemon> "GitHub: searls/matt-daemon") project
  - The [jason-bourne-shell](<https://github.com/bostonaholic/jason-bourne-shell> "GitHub: bostonaholic/jason-bourne-shell") project
    - The [json-bourne-shell](<https://github.com/Breton/json-bourne-shell> "GitHub: Breton/json-bourne-shell") project

---

This idea was previously mentioned on
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
by [Vincent Mühler](<https://medium.com/@muehler.v> "Medium: Vincent Mühler")).
