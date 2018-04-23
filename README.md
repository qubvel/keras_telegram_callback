## Keras callback in Telegram
Telegram-bot callback for your Keras model  

This module allows your model to send learning history to your chat in Telegram messenger.  

### Configure your Telegram Callback
To start use this callback you need fo register bot in telegram and get your `telegram_id`. Follow instructions below.

#### Step 1. Register your telegram bot.  
 - Find `BotFather` in Telegram.
 - Follow `BotFather` instructions to register your bot in a few steps and get `token`.

#### Step 2. Get your ID.
 - Find your bot in telegram and send message 'hello!'
 - Paste in your browser `api.telegram.org/bot<token>/getUpdates` (use token you get in previous step), if you did everything correctly you will recive a JSON where you can find your `telegram_id`.

### Example

```
from .callbacks import TelegramCallback

# load data, define and compile model
...

# create callback
config = {
    'token': '556983321:AAHO-bSWaIqcvHL91Xw12X18OWczFIpY1s0',   # invalid token, paste here your own token
    'telegram_id': 123456789,
}

tg_callback = TelegramCallback(config)

# start training
model.fit(x, y, batch_size=32, callbacks=[tg_callback])
```

Congratulations! Now you will recive logs (losses, metrics, lr, etc.) in Telegram!
