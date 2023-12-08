# Telegram Bot on Cloudflare Workers to forward message to flomo

This is a fork from the [cvzi's telegram bot example](https://github.com/cvzi/telegram-bot-cloudflare/tree/main). 

This code has been updated to forward message from Telegram Bot to [flomo](https://flomoapp.com/)

## Setup:

1. Get your new bot token from [@BotFather](https://t.me/botfather): https://core.telegram.org/bots#6-botfather
2. Sign up to Cloudflare Workers: https://workers.cloudflare.com/
3. In the Cloudflare Dashboard go to "Workers", then click "Create application" and then "Create worker"
4. Choose a name and click "Deploy" to create the worker
5. Click on "Configure worker" -> "Settings" -> "Variables"
6. Add a new variable with the name `ENV_BOT_TOKEN` and the value of your bot token from [@BotFather](https://t.me/botfather)
7. Add a new variable with the name `ENV_BOT_SECRET` and set the value to a random secret. See https://core.telegram.org/bots/api#setwebhook
8. Add a new variable with the name `ENV_FLOMO_API_URI` and set the value to your flomo API. See https://help.flomoapp.com/advance/api.html
9. Click on "Quick Edit" to change the source code of your new worker
10. Copy and paste the code from [bot.js](bot.js) into the editor
11. Optional: Change the `WEBHOOK` variable to a different path. See https://core.telegram.org/bots/api#setwebhook
12. Click on "Save and Deploy"
13. In the middle panel append `/registerWebhook` to the url. For example: https://my-worker-123.username.workers.dev/registerWebhook
14. Click "Send". In the right panel should appear `Ok`. If 401 Unauthorized appears, you may have used a wrong bot token.
15. That's it, now you can send a text message to your Telegram bot

## Bot behaviour

The bot will foward your text message to your flomo account.



