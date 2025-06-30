
## 📦 Install

```sh
npm i node-telegram-bot-api
```

<br/>

> ✍️ **Note:** If you use Typescript you can install this package that contains type definitions for this library
>```sh
>npm install --save-dev @types/node-telegram-bot-api
>```

## 🚀 Usage

```js
const TelegramBot = require('node-telegram-bot-api');

// replace the value below with the Telegram token you receive from @BotFather
const token = 'YOUR_TELEGRAM_BOT_TOKEN';

// Create a bot that uses 'polling' to fetch new updates
const bot = new TelegramBot(token, {polling: true});

// Matches "/echo [whatever]"
bot.onText(/\/echo (.+)/, (msg, match) => {
  // 'msg' is the received Message from Telegram
  // 'match' is the result of executing the regexp above on the text content
  // of the message

  const chatId = msg.chat.id;
  const resp = match[1]; // the captured "whatever"

  // send back the matched "whatever" to the chat
  bot.sendMessage(chatId, resp);
});

// Listen for any kind of message. There are different kinds of
// messages.
bot.on('message', (msg) => {
  const chatId = msg.chat.id;

  // send a message to the chat acknowledging receipt of their message
  bot.sendMessage(chatId, 'Received your message');
});
```



We also have a [Telegram  group][tg-group] to discuss issues related to this library.

Some things built using this library that might interest you:

* [tgfancy](https://github.com/GochoMugo/tgfancy): A fancy, higher-level wrapper for Telegram Bot API
* [node-telegram-bot-api-middleware](https://github.com/idchlife/node-telegram-bot-api-middleware): Middleware for node-telegram-bot-api
* [teleirc](https://github.com/FruitieX/teleirc): A simple Telegram ↔ IRC gateway
* [bot-brother](https://github.com/SerjoPepper/bot-brother): Node.js library to help you easily create telegram bots
* [redbot](https://github.com/guidone/node-red-contrib-chatbot): A Node-RED plugin to create telegram bots visually
* [node-telegram-keyboard-wrapper](https://github.com/alexandercerutti/node-telegram-keyboard-wrapper): A wrapper to improve keyboards structures creation through a more easy-to-see way (supports Inline Keyboards, Reply Keyboard, Remove Keyboard and Force Reply)
* [beetube-bot](https://github.com/kodjunkie/beetube-bot): A telegram bot for music, videos, movies, EDM tracks, torrent downloads, files and more.
* [telegram-inline-calendar](https://github.com/VDS13/telegram-inline-calendar): Date and time picker and inline calendar for Node.js telegram bots.
* [telegram-captcha](https://github.com/VDS13/telegram-captcha): Telegram bot to protect Telegram groups from automatic bots.


## 👥 Contributors

<p align="center">
  <a href="https://github.com/yagop/node-telegram-bot-api/graphs/contributors">
    <img src="https://contrib.rocks/image?repo=yagop/node-telegram-bot-api" />
  </a>
</p>

## License

**The MIT License (MIT)**


<div align="center">

A telegram 🤖 bot for music, videos, movies, EDM tracks, torrent downloads, files and more.

[![https://t.me/beetube_bot](https://img.shields.io/badge/🤖%20Telegram-Bot-neon.svg)](https://t.me/beetube_bot) [![https://t.me/beetubers](https://img.shields.io/badge/💬%20Telegram-Channel-blue.svg)](https://t.me/beetubers) [![Beetube CI](https://github.com/kodjunkie/beetube-bot/workflows/Beetube%20CI/badge.svg)](https://github.com/kodjunkie/beetube-bot/actions) <a href="https://github.com/kodjunkie/beetube-bot/blob/master/LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" height="20"></a>

</div>

<details>
 <summary><b>Table of Content</b></summary>

- [Demo](#demo)
- [Features](#features)
- [Installation](#installation)
  - [Telegram setup](#telegram+setup)
  - [Install on system](#install+system)
  - [Install via docker](#install+docker)
  - [Install via docker compose](#install+docker+compose)
- [Liked it?](#liked+it)
- [Tests](#tests)
- [License (MIT)](#license)

</details>

## Demo

The deployed version can be found on telegram as <a href="https://t.me/beetube_bot" target="_blank">@beetube_bot</a>

- [View Demo 1](https://github.com/kodjunkie/beetube-bot/blob/master/assets/demo-one.gif)
- [View Demo 2](https://github.com/kodjunkie/beetube-bot/blob/master/assets/demo-two.gif)

## Features

- Browse, search and download `movies`, `music`, `anime` and `torrent`
- Ability to browse `music` sorted by genre
- Ability to download `music` directly from chat
- Ability to paginate all returned results
- Supports personalized configurations

## Installation

> Beetube by default have been setup for easy deployment on <a href="https://heroku.com/" target="_blank">heroku</a>

### Requirements

- Nodejs >= `v14.x`
- MongoDB (database)
- Have <a href="https://github.com/kodjunkie/node-raspar" target="_blank">node-raspar</a> deployed and note the server `address`

<a name="telegram+setup"></a>

### Telegram Setup (required)

1.  Create a new bot via <a href="https://telegram.me/BotFather" target="_blank">@BotFather</a> and note the `token`
2.  Type `/setcommands`
3.  Select the bot you just created
4.  Copy and paste the texts below as the bot's commands

```
  start - start a conversation with the bot
  search - search through any category
  keyboard - show custom keyboard
  about - about this bot
```

<a name="install+system"></a>

### Install on Local Machine

```bash
$ git clone https://github.com/kodjunkie/beetube-bot.git
$ cd beetube-bot
$ cp .env.example .env # update .env accordingly
# install dependencies
$ npm install
# have mongodb daemon running
# start the bot
$ npm start
```

<a name="install+docker"></a>

### Installation via Docker

```bash
$ git clone https://github.com/kodjunkie/beetube-bot.git
$ cd beetube-bot
$ cp .env.example .env # update .env accordingly
#
# build the container
$ docker build -t beetube-bot .
# run the container
$ docker run --name beetube --env-file=.env -it beetube-bot
```

<a name="install+docker+compose"></a>

### Installation via Docker Compose

```bash
$ git clone https://github.com/kodjunkie/beetube-bot.git
$ cd beetube-bot
$ cp .env.example .env # update .env accordingly
#
# To boot-up first time only
# Or whenever docker file is modified (builds the container)
$ docker compose up --build
# To boot-up without building the container (regular use)
$ docker compose up
# To shut-down
$ docker compose down
```

<a name="liked+it"></a>

## Liked it?

Hope you liked this project, don't forget to give it a star ⭐

<div align="center">
  <a href="https://starchart.cc/kodjunkie/beetube-bot">
    <img src="https://starchart.cc/kodjunkie/beetube-bot.svg" width="600px">
  </a>
</div>

## Tests

```bash
$ npm test


Copyright © 2025 Yago
