triviabot
=========

A simple IRC trivia bot written in python using twisted.

Features
--------

Simple implementation. Questions are <string>`<string> formatted in plain text files.

Configurable colored text to help differentiate game text from user text.

Event driven implementation: uses very little cycles.

Implementation
--------------

triviabot uses a config.py and comes with an example for you to tweak and use.

Questions exist in files under $BOTDIR/questions.
Each round, a file is selected at random, then a line is selected at random from the file.

The answer is then masked and the question is asked. Periodically, the bot will ask the current question
again and unmask a letter. This happens three times before the answer is revealed.

What the bot doesn't do.
------------------------

  * It doesn't have multiple answers to a question. It shows you the format. Part of the game is to match its formatting.

  * Have error-free questions: the questions come from other bot implementations which themselves had horrible typos.
There needs to be an army of editors to go through the 350+k lines and format them to the standard format for the bot.
The bot was written to catch malformed questions so it wouldn't crash, but if it technically matches <string>`<string>
there's no way for the bot to understand that's not part of the question.


Todo:
-----

Look at the issues. Pull requests welcome.


Contact, Support, Development:
------------------------------

Quakenet IRC - #triviabot-dev
http://webchat.quakenet.org/?channels=triviabot-dev

GitHub Issues/Tickets
https://github.com/rawsonj/triviabot/issues


License:
--------

Released under the GPLv3.

Changes in this fork:
---------------------
- Added option for channel key (password)
- Added QuakeNet Q functionality, namely AUTH and mode +x
- Added option to remove repetition of question on each clue (less clutter)
- Added Jeopardy trivia question pack (source see below)
- Added Log file

Addition of Jeopardy questions:
-------------------------------
I added Jeopardy trivia questions, that were pulled from a JSON file found in the GitHub Repo
https://github.com/epitron/trebek/tree/master/questions
The questions were parsed into files of 5000 questions each, including date & money worth.