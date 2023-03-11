<div align="center">

# Simple bot to interact with Reddit via Selenium with Chromedriver

![Python Versions](https://img.shields.io/badge/python-3.6%20%7C%203.7%20%7C%203.8%20%7C%203.9%20%7C%203.10%20%7C%203.11-blue)
![License](https://img.shields.io/badge/license-MIT-brightgreen)

</div>

## Usage

Currently supported interacions:

- login
- upvote/downvote post
- comment under post
- join/leave community

## Usage

Download the latest chromedriver here https://chromedriver.chromium.org/downloads and extract `chromedriver.exe` in the same directory as this script.

### Using command line arguments

    > py main.py -h

Available flags:

    -h, --help:
        Show this help message and exit.

    -l, --links:
        [path] File containing liks and actions. The file should be a list of links, one per line, following the structure: url|action|comment (if action is comment). Actions can be one of the following: upvote, downvote, comment, join, leave. The file should be in the same directory as this script.

    -a, --accounts:
        [path] File containing credentials for accounts to perform the actions with. The file should be a list of usernames and passwords, one per line, following the structure: username|password. The file should be in the same directory as this script.

    -v, --verbose:
        [none] Print INFO messages to stdout.

#### Examples:

This will log into account, reject non-essential cookies, upvote the first post, downvote the second one and comment under it, join "r/ProgrammerHumor" community then leave it.

    > py main.py --accounts accounts.txt --links posts.txt

where accounts.txt looks like this:

    lachezarnaa|zarazarazara

and posts.txt looks like this:

https://www.reddit.com/r/rainworld/comments/11nefg8/why_is_this_guy_worth_7_points_lil_baby_centipede/?utm_source=share&utm_medium=web2x&context=3|upvote
https://www.reddit.com/r/ProgrammerHumor/comments/z8ghv8/gotta_save_those_characters/|downvote
https://www.reddit.com/r/ProgrammerHumor/comments/z8ghv8/gotta_save_those_characters/|comment|sad
https://www.reddit.com/r/ProgrammerHumor/|join
https://www.reddit.com/r/ProgrammerHumor/|leave
