# Initial bringups for nim-tg-manager

### Before you start

Clone this repo `git clone https://github.com/rupansh/nim-tg-manager`

Make a file called config.ini and while referring to example-config.ini, do the following-

Get your bot api key from BotFather.
Set Owner ID and Sudo ID(s)
Create an empty channel with any random username and set its username in CHANNEL_USER (***Mandatory btw***)


Install redis on your machine/server (Windows/OSX/Linux) and start it!

Finally, compile and run the bot
`cd nim-tg-manager`
`nimble build -d:release`

## Starting the bot

Once you've setup your redis and config:

`./tg_manager`
