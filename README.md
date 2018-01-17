# Tattle

Tattle - a Discord bot for transparency in Reddit moderation

## Features

* Post all removals from a Reddit audit log to a Discord channel
* Assign each case a reason for removal
* Get alerts for repeat offenders

## Config

Before you can use the bot, you need to fill in config information in
`config.json` like this:

```
{
	"reddit":
	{
		"client_id": "REDDIT APPLICATION CLIENT ID",
		"client_secret": "REDDIT APPLICATION CLIENT SECRET",
		"user_agent": "Tattle v2",
		"username": "REDDIT ACCOUNT NAME",
		"password": "PASSWORD"
	},
	"discord": "DISCORD BOT USER TOKEN",
	"subreddit": "SUBREDDIT NAME",
	"removed_posts": "CHANNEL ID FOR REMOVAL LOGS",
	"sub_mod_talk": "CHANNEL ID FOR USER ALERTS",
	"alert_role": "ROLE TO PING FOR USER ALERTS"
}
```

The Reddit account needs to be the developer of the Reddit application,
and be on the moderator list for the monitored subreddit (even if there
are no permissions granted - any moderator can see the logs, which is
all the bot needs).  The Discord bot user needs to have a **role** that
can read and send messages in both of the channels given - per-user
permissions seem to screw something up.

## Commands

The bot will only process messages from server administrators.

```t:about```

Shows copyright information.

```t:clear USER```

Strikes every case associated with the given user.  See t:strike.

```t:help```

Shows this list of commands.

```t:info USER```

Shows all of a user's cases.

```t:justify # REASON...```

Sets the reason field of a case.

```t:list```

Lists all tracked users and their removal counts.

```t:show #```

Sends an untracked copy of a case's info.

```t:strike #```

Strikes the given case.  A stricken case will have its log removed, and will not count against the OP.  This is Arnie's favourite command.

## License

Tattle - a Discord bot for transparency in Reddit moderation

Copyright 2017, 2018 Declan Hoare

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
