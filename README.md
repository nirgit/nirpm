# Creating the Project
First things first: let’s create a new project. Create a directory for the project, enter it and run npm init to initialise the new project with a package.json file. Answer the prompts if you wish, or just hit enter a bunch of times to get a template package.json file that you can fill out at your own leisure.

## Editing package.json
The package.json file is used by npm, Node’s package manager, to know about your project, its dependencies and how it works. We need to make a couple of edits to it.

remove the main entry: this is only used for modules that will be used through the module system (e.g. var _ = require('underscore');).
You can add "preferGlobal" and set it to true, which means if someone installs this module through npm and doesn’t use the --global option, they will be warned that the module is designed to be installed globally.
add the bin object, which maps commands to files. This means when this module is installed, npm will set up the runnir executable to execute index.js.
```
{
  "name": "runnir",
  "version": "1.0.0",
  "description": "searches for files",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "JavaScript Playground",
  "license": "ISC",
  "preferGlobal": true,
  "bin": {
    "runnir": "index.js"
  }
}
```
Creating the Script.

Create index.js and add this to the top:

```
#! /usr/bin/env node
console.log('This is the runnir script.');
```
## Installing the Script
Now in your project you can run ```npm link``` to install the script on your system. This creates a symlink to your project so that you can run the project whilst working on it, with no need to keep reinstalling it over and over again.

Once npm link has run, you should be able to run runnir on the command line and see the string printed back.
