# Initial bringups for Paperplane

### Before you start

Clone this repo `git clone https://github.com/RaphielGang/Telegram-UserBot`

Install all the requirements with pip `pip3 install -r requirements.txt`

Get your api-id (called `API_KEY` in this bot) and API_HASH from my.telegram.org.

Install all the requirements by running `pip3 install -r requirements.txt`

Optional: Create an empty group, add Marie, or any forks, get the group id, copy it and set it as your `LOGGER` (in case you want logging).

### Database

If you wish to use a database-dependent module (eg: locks, notes, userinfo, users, filters, welcomes), you'll need to have a database installed on your system. I use Postgres, so I recommend using it for optimal compatibility.

In the case of postgres, this is how you would set up a the database on a Debian and its derivatives system. Other distributions may vary.

- Install PostgreSQL:

`sudo apt-get update && sudo apt-get install postgresql`

- Change to the Postgres user:

`sudo su - postgres`

- Create a new database user (change YOUR_USER appropriately):

`createuser -P -s -e YOUR_USER`

This will be followed by you needing to input your password.

- Create a new database table:

`createdb -O YOUR_USER YOUR_DB_NAME`

Change YOUR_USER and YOUR_DB_NAME appropriately.

- Finally:

`psql YOUR_DB_NAME -h YOUR_HOST YOUR_USER`

This will allow you to connect to your database via your terminal. By default, YOUR_HOST should be 127.0.0.1:5432.

You should now be able to build your database URI. This will be:

`sqldbtype://username:pw@hostname:port/db_name`

Replace sqldbtype with whichever db youre using (eg PostgreSQL, mysql, sqllite, etc)
repeat for your username, password, hostname (localhost?), port (5432?), and db name.

### Configuration

There are two possible ways of configuring your bot: a config.env file, or ENV variables.

The prefered version is to use a `config.env` file, as it makes it easier to see all your settings grouped together.
This file should be placed in the topmost part of the repo.
This is where your `API KEYS` will be loaded from, as well as your `database URI` (if you're using a database), and most of
your other settings.

An example `config.env` file could be:
```
    API_KEY=123456
    BUILD_CHOICE="bleeding"
    API_HASH='4588acb1863ead924119c885dfffba2'
    LOGGER_GROUP=-1001200493567
    LOGGER=True    #Incase you want to turn off logging, put this to false
    TRT_ENABLE=False
    PM_AUTO_BAN=True
    CONSOLE_LOGGER_VERBOSE=True
    SCREEN_SHOT_LAYER_ACCESS_KEY="get from screenshot layer website google it "
    OPEN_WEATHER_MAP_APPID="get it from openweather site"
    DB_URI="postgres://userbot:mypass@localhost:5432/userbot"
```

If you can't have a config.env file, or you missed to type something on `config.env` but then pushed it up, it is also possible to use environment variables.


## Starting the bot

Once you've setup your database and your configuration (see below) is complete, simply run:

`python3 -m userbot`