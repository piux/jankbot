# Jankbot
A Steam bot for Dota 2 communities

## Introduction
Jankbot is an open source module-oriented Steam bot designed to help organize
player communities. The system is open for use and devleoped with scale in mind
so that any size group can make use of it. Jankbot is written in NodeJS.

## Installation
You will need:
* NodeJS v0.10.x or higher
* NPM (comes with node)
* A Steam account with full privilages

Keep in mind that in order to have a full privilaged Steam account, you must
make at least one transaction on the account. If you do not do this, you will
not be able to add the bot to your friends list.

To begin, download the Jankbot source. Using a terminal, cd into the source
directory and run `npm install`.

**NOTE:** You may have issues installing the node packages for Steam. It is
recommended that you use a linux operating system and use NodeJS v0.10.x

Once the packages are installed, you will need to set up the config file.
Create a file called `config.json` and use this template:

```javascript
{
  "username": "your_bot_account_username",
  "password": "your_bot_account_password",
  "admins" : [],
  "modules" : [
  ],
  "displayName" : "Jankbot"
}
```

Once you edit the config file with the proper username and password, you're set!
Run your newly installed Jankbot with `node jankbot` and you should be ready to
roll!

## Adding Modules
Jankbot is designed to use custom modules to extend his abilities. To add a
module, begin by placing the module source file in the `bot_modules/` directory.
Then, edit `config.json` and add the name of the module to the `modules`
property.

For example, if you were adding a module called "quotes" with a source file
`quotes.js`, your config.json file would look like this:

```javascript
{
  "username": "your_bot_account_username",
  "password": "your_bot_account_password",
  "admins" : [],
  "modules" : [
    "quotes"
  ],
  "displayName" : "Jankbot"
}
```

To add more modules, simply repeat the same steps and add the names of the
modules to your config file. **Be sure to use commas to separate the module
names!**

## Administrating Your Jankbot
To use the admin commands, you will need to let Jankbot know who is an admin. To
do this, you will need to add the Steam ID numbers to the config file. To find
out your steam ID number, run Jankbot and message him saying "ping". Jankbot
will respond saying "pong" and your Steam ID.

Once you have your Steam ID, add it to the `admins` property in the config file.
If your steam ID was 12345654321, your config file would look like this:

```javascript
{
  "username": "your_bot_account_username",
  "password": "your_bot_account_password",
  "admins" : ["12345654321"],
  "modules" : [
  ],
  "displayName" : "Jankbot"
}
```

To add more administrators, simply add their Steam IDs to the list, separating
by commas.

## FAQ
**Why won't Jankbot accept friend requests?**
You need to be sure that the account Jankbot is using has full permissions. You
must make at least 1 transaction on the account to make use of friends lists.

**How do I keep Jankbot running after I close the terminal?**
You may want to look into [forever](https://github.com/nodejitsu/forever). It
will keep scripts running...well, forever.

**What will happen if I delete the friends or logger modules?**
Puppies around the world will die and Jankbot will not be able to function.
Those modules are part of the core of Jankbot and are there to be used by other
modules.

**How do I update Jankbot?**
Updating Jankbot is as simple as replacing the files. Just make sure you don't
delete or overwrite any module data files like `friendslist`. Soon enough a
patch system will be put in place and Jankbot will be able to update himself.
Remember that you will need to restart Jankbot after updating.

**Why is Jankbot a 'he'?**
By all means, refer to Jankbot as Jankettebot. Just feels easier saying 'he'
instead of 'it' or 'Jankbot' all the time.

## License
Copyright (c) 2013 Michael Barrett, JankDota.com

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
