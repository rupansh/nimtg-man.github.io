Current Commands
=============

# Management

- `promote` (Admins only) : reply with `/promote` to a message to promote the sender (`/promote <id>` works as well)

- `demote` (Admins only) : reply with `/demote` to a message to demote the sender (`/demote <id>` works as well)

- `pin` (Admins only) : reply with `/pin` to a message to pin a message in the group

- `unpin` (Admins only) : send `/unpin` to unpin currently pinned message

- `invite` : send `/invite` to get a unique invite link for the group

- `admins` : send `/admins` to get a list of admins

# Restrictions

- `ban` (Admins only) : reply with `/ban` to a message to ban the sender

- `tban` (Admins only) : reply with `/tban <time>` to a message to temporarily ban for the specified time.
Valid time format: 1d, 2d, 30m, 1h, 4h, etc..

- `banme` : send `/banme` to ban yourself

- `unban` (Admins only) : reply with `/unban` to a message to unban the sender

- `kick` (Admins only) : reply with `/kick` to a message to kick the sender

- `kickme` : send `/kickme` to kick yourself

- `mute` (Admins only) : reply with `/mute` to a message to mute the sender

- `tmute` (Admins only) : reply with `/tmute <time>` to a message to temporarily mute the sender for the specified time.
Valid time format: 1d, 2d, 30m, 1h, 4h etc..

- `unmute` (Admins only) : reply with `/unmute` to a message to unmute the sender

- you can use `<command> arguments(if any) <userid>` for these as well. eg `/tmute 1h 88119` or `/mute 88119`

# Info stuff

- `id` : send `/id` to get the group's id, reply to a user/bot's message to get their id

- `info` : send `/info` to get information about yourself, reply to a user/bot's message to get information about them

- `ping` : send `/ping` to ping telegram api and get the time in ms

# Messages

- `purge` (Admins only) : reply with `/purge` to delete all the messages till that point

- `del` (Admins only) : reply with `/del` to delete a message

# Stickers

- `getsticker` : reply with `/getsticker` to a sticker to fetch it in downloadable webp format(with png extension to fool api)

- `kang` : Do i really need to tell you anything? :D. supports images as well

# Blacklist

- `addblacklist` (Admins only) : send `/blacklist <string>` to blacklist a string. where string is any valid unicode string. Any message with the blacklisted string is deleted automatically

- `rmblacklist` (Admins only) : send `/rmblacklist <string>` to remove it from blacklist

- `getblacklist` : send `/getblacklist` to get a list of active strings in blacklist

# Flood check

- `setflood` (Admins only) : send `/setflood <integer>` to set floodlimit in the chat. A user is auto banned
if they exceed the limit

- `clearflood` (Admins only) : send `/clearflood` to clear the flood setting

- `getflood` (Admins only) : send `/getflood` to get the current flood setting

# Notes

- `save` (Admins only) : reply with `/save` to any message(Including media) to add it to notes

- `get` : send `/get <notename>` to fetch a note

- `clear` (Admins only) : send `/clear` to clear all notes

- `saved` : send `/saved` to get a list of notes

# Gbans

- `gban` (Sudo/Owner only) : reply with `/gban` to any message or send `/gban <userid>` to gban a person.
The person is automatically banned if they are found in a chat with the bot

- `ungban` (Sudo/Owner only) : reply with `/ungban` to any message or send `/ungban <userid>` to ungban a person. The person is unbanned from previously banned groups(Only where they were banned because of gban filter)

- `gmute` (Sudo/Owner only) : reply with `/gmute` to any message or send `/gmute <userid>` to gmute a person.
The person person is automatically muted if they are found in a chat with the bot

- `ungmute` (Sudo/Owner only) : reply with `/ungmute` to any message or send `/ungmute <userid>` to remove a person from gmute list. The person is unmuted from previously muted groups(Only where they were muted because of gmute filter)

# Rules

- `setrules` (Admins only) : reply with `/setrules` to a message to set the rules for the group( `/setrules <message> works as well` )

- `rules` : send `/rules` to get the rules of the group

# Intro

- `start` : send `/start` and the bot will greet you

# Memes

- some reference taken from skittbot

- `owo` : reply with `/owo` to a message to get owo-ified text
- `stretch`: reply with `/stretch` to a message to get stretched text
- `mock` : reply with `/mock` to a message to get spongemock text
- `zalgo` : reply with `/zalgo` to a message to get zalgofied text