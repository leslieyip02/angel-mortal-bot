# Angel and Mortals Bot

Forked from [https://github.com/kstonekuan/angel-mortal-bot](https://github.com/kstonekuan/angel-mortal-bot).

## Setup

1. Configure `players.csv`

The pairings follow the format below:

```
Player,Angel,Mortal
```

For the names, do not include the `@`.

2. Configure `.env`

Get an API token from [https://t.me/BotFather](https://t.me/BotFather).

```
ANGEL_BOT_TOKEN=<API token here>
PLAYERS_FILENAME='players.csv'
CHAT_ID_JSON='logs.json'
ANGEL_ALIAS='Care Bear'
MORTAL_ALIAS='Gummy Bear'
```

3. Configure `systemd` service

```
# set up environment
python -m venv .venv
pip install -r requirements.txt

# configure service
sudo cp bot.service /etc/systemd/system/bot.service
sudo systemctl enable bot.service
sudo systemctl start bot.service

# check logs
sudo systemctl status bot.service
```

Follow instructions from [here](https://blog.merzlabs.com/posts/python-autostart-systemd/). Edit the path to the `.venv` and `bot.py` files as necessary.