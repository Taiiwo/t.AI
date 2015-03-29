t.AI
====

Description
-----------
t.AI is a set of tools that collect data from a source, store it, and allow it's retrieval in the form of natural language. This will hopefully create a natural language AI that can learn from a given media, and actually be a useful interface for things like information bots and such. For example, if the t.AI was fed information from an IRC channel, it could collect spoken information, and when questions are asked about subject that t.AI has collected, the bot could respond with the relevant information without their having to be users in the channel to answer questions that have already been answered.

AI Collection Core - AICC
-------------------------
AICC will be flexible enough to collect data from all sources. There should be separate scripts to use the AICC to do more common tasks like scrape websites, irc, certain file types, etc. AICC will use a plug-in based system to match certain sentence structures and convert them into information that can be stored in the AISU.

AI Storage Unit - AISU
----------------------
The AISU will be an MySQL database with the following fields.

| Author      | Data                        | Parents           | Subject | Property  |
|-------------|-----------------------------|-------------------|---------|-----------|
| Taiiwo      | I like cake                 | Taiiwo            | Likes   | Cake      |
| testPerson  | The sky is blue             | Sky               | Colour  | Blue      |
| crashDummy  | Gabe's dog's name is buddy  | Gabe, Gabe's dog  | Name    | Buddy     |

So to bring up all data on 'Taiiwo', we simply search all fields with 'Taiiwo' in the 'Parents' field. To bring up everyone who likes cake, search for 'likes' as the subject, and 'cake' as the topic.

AI Interface - AII
------------------
The AII will be a regex-based plugin system. When a query is matched by one of the plugins, that plugin runs an SQL query to find the relevant data, and if it exists, the interface will return a preset natural language response.
