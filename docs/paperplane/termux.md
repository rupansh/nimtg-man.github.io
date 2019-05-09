# Running on TermUX

> Although this was originally designed to run on linux distros ( maybe windows meme too).. you can also run userbot on your Android smartphones. this actually comes handy, if you don't have any server host.. or you just want to try. Assuming you have basic linux cmd & bash knowledge, and have [Termux](https://play.google.com/store/apps/details?id=com.termux) installed

**Make sure to enable Storage permission of termux, otherwise it'll give you error when accessing SDCard**

### Installing requirements:
- Install build packages

`apt-get update; apt-get upgrade`
`apt-get install zlib zlib-dev curl wget libwebp libwebp-dev libjpeg*`
`pkg install clang curl python python-dev postgresql-dev libcrypt-dev libffi-dev openssl-dev libxml2-dev libxslt-dev libjpeg-turbo-dev ndk-sysroot make`

`pkg upgrade`

- Clone bot sources

`git clone https://github.com/baalajimaestro/Telegram-UserBot.git`

- Install python dependencies

`cd Telegram-UserBot`

`pip install -r requirements.txt`

### Creating Config:
a config file is used to configure your userbot.. it contains your api keys, db url and other settings. here is one [sample_config](../blob/master/sample_config.env)

this is little bit tricky.. as Termux doesn't have proper way to edit files
- copy config to sdcard

` cp sample_config.env /sdcard/config.env`

now you can edit config.env on sdcard with any text editor.. i prefer [Jota+ (text editor)](https://play.google.com/store/apps/details?id=jp.sblo.pandora.jota.plus)

carefully fill up all the details. `API_KEY`and `API_HASH` can be grabbed from [Here](https://my.telegram.org/apps). if u want to log your stuffs(optional), set `LOGGER` to true and add your group ID in `LOGGER_GROUP`

if you want to use a database (optional) with your bot, then add your database url in `DATABASE_URL`, otherwise leave empty. Guide to create your database is also given below

- Now lets move our config to bot source

`cp /sdcard/config.env ~/Telegram-userbot`

### Lets run it:
assuming you have followed all above steps.. and installed all requirements

- generate userbot session

`python -m userbot test`

- **finally run it**

`python -m userbot`

if everything worked great.. your bot should be running now. type _.alive_ on any chat to check.

### Running your bot with a Database:
while you can run your bot without any DB, having a Database will give you access to more powerful features of your userbot, like auto manage of your pm, notes saving, filters etc.
fortunately you can create a database with termux

- install postgresql

`pkg install postgresql readline`

- initialize skeleton database

`mkdir -p $PREFIX/var/lib/postgresql`

`initdb $PREFIX/var/lib/postgresql`

- now start the sql server

`pg_ctl -D $PREFIX/var/lib/postgresql start`

- create new database & user

`createdb botdb`

`createuser botuser`

your database is now up and running. to add this database in your userbot, u have to add its url to `DATABASE_URL` on config.env

a typical database url looks like that:

`sqldbtype://username:pw@hostname:port/db_name`

Replace sqldbtype with whichever db you're using (eg postgres, mysql, SQlite, etc) repeat for your username, password, hostname (localhost?), port (5432?), and db name. password can be left empty.. if not set.

**for above tutorial, our URL will be like this:**

`postgresql://botuser:@localhost:5432/botdb`

just remember that each time, you have to run your sql server first.. then your userbot

to start sql server, run `pg_ctl -D $PREFIX/var/lib/postgresql start` and then `python -m userbot` to run userbot

to stop your userbot, run `killall postgres` to first stop sql server, then `killall python` for bot