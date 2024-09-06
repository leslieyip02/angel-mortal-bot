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

# add service
sudo systemctl --force --full edit bots.service

sudo systemctl daemon-reload
sudo systemctl enable bot.service
```

Follow instructions from [here](https://blog.merzlabs.com/posts/python-autostart-systemd/).