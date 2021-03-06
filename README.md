# TV Show Telegram Bot

This creates a TV Show script database(sqlite) with timestamps using .srt files. If you order your .srt files by episode number **subtitle_to_database.py** will create a 2-table relational database for you. The name of the .srt files will be inserted into *episode_id* table.

Then you can create your own Telegram bot using this database. All telegram bot source code is in the /telegram folder. Don't forget to create your own telegram bot token via [BotFather](https://telegram.me/BotFather)

You can also use the English .srt [database](/db) created for my favorite show [It's Always Sunny in Philadelphia](https://www.imdb.com/title/tt0472954/). 

When a user types `/line [Line from the show]` the bot will find that line in the show and it will return with season, episode number, episode name, exact time from the discussion and a url to stream that particular episode.  
  
If you woud like to use sqlite **FTS5** features such as full-text search use the *lines* virtual table. Otherwise you can use the *subtitle* table.

You are all set after you add your token [here](/telegram.config.cfg).

### Required Packages
**For SQlite FTS5 features:**  
`pip install peewee`
  
### Run
`python telegram/server.py`  
  
### Command List:
  
**/line** - Enter a line from the show to find the episode.  
Usage: /line your line  
  
**/episodes** - Get the list of episodes from a season.  
Usage: /episodes season_number  
  
**/random** - Get a random episode from the show.  
Usage: /random  

**/sunny_help** - Returns the command list  

**/trivia** - Returns a trivia about the show

**Extra Features**:
- If you add the bot to a group it will welcome the newcomer with an [ocular pat down](https://www.urbandictionary.com/define.php?term=ocular%20pat%20down)  
- If a user leaves the group it will send this [gif](https://media.giphy.com/media/BLvZWddnwvcwE/giphy.gif) both to the group and the user.
- Logs bot interactions only if it starts with / character.

**Possible Features**:
- `start_time` and `end_time` can be used to cut a wanted video scene from the episode then can be converted to gif and showed on Telegram.

If you are ready to go live, check-out [where to host Telegram bots](https://github.com/python-telegram-bot/python-telegram-bot/wiki/Where-to-host-Telegram-Bots). Please feel free to change and use it in any way you would like to!  
