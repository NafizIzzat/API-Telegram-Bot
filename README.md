# Set Up A Notification Bot With Telegram App
Steps to create a simple notification bot using telegram's API, adding the bot to a group chat, deploying it to a free cloud server, letting it run forever till the day humans are replaced by actual AI bots.

## The Configuration
1. Download Telegram App: [Telegram for MacOS](https://macos.telegram.org/)
2. Open App and search for @botfather
3. In the @botfather chat:
    1. Type `/start` to begin. You will get a list of commands.
    2. Type `/newbot` to create new bot.
    3. Type in your bot display name.
    4. Type in your bot username which needs to end with `bot` and is unique.
    5. If everything is done right, you will get:
        - A link: `t.me/i_am_from_the_future_bot`
        - An access token: `686904521:AAELuhRC8POKE1obIkb3O1MOPi4weMLRBRyf`
    6. Go to `https://api.telegram.org/bot<token>/getUpdates`.
        - Replace `<token>` with the access token you received earlier.
        - You should get a JSON similar to: `{"ok":true,"result":[]}`
    7. Go back to the Telegram app, click the link to go to your bot's chat and click `Start`.
    8. Type in `Hello` and `Test` to check if the bot is capturing data. Test a couple of times periodically. I tried twice before if gave any results.
    9. Refresh the page at step vi.
        - You should get a JSON similar to: `{
  "ok": true,
  "result": [
    {
      "update_id": 481198457,
      "message": {
        "message_id": 3,
        "from": {
          "id": 237552982,
          "is_bot": false,
          "first_name": "Nafiz",
          "last_name": "Izzat",
          "username": "NafizIzzat",
          "language_code": "en-MY"
        },
        "chat": {
          "id": 237552982,
          "first_name": "Nafiz",
          "last_name": "Izzat",
          "username": "NafizIzzat",
          "type": "private"
        },
        "date": 1535214449,
        "text": "Test again"
      }
    }
  ]
}`

    10. You now have a working API connecting you to your bot. Take note of your `"id": 237552982` in your JSON.
    11. Lets test and send a request straight through the API:
        - `https://api.telegram.org/bot<token>/sendMessage?chat_id=237552982&text=Helloo`
        - Replace <token> with the access token you received earlier.
        - Replace <id> with the id from the JSON you received earlier.
        - Check out the documentation for more info: [Telegram send message](https://core.telegram.org/bots/api#sendmessage)
        - You should get a JSON similar to: `{
  "ok": true,
  "result": {
    "message_id": 4,
    "from": {
      "id": 686104231,
      "is_bot": true,
      "first_name": "Test Bot",
      "username": "i_am_from_the_future_bot"
    },
    "chat": {
      "id": 237552982,
      "first_name": "Nafiz",
      "last_name": "Izzat",
      "username": "NafizIzzat",
      "type": "private"
    },
    "date": 1535216846,
    "text": "Helloo"
  }
}`
        - You should get a text and a notification from your bot in the Telegram App too.
    12. The setup is complete now to code.
    13. If you want to add the bot to a group, just add the bot by its username to any existing group.

## Code A Basic Task
1. Run the `requirements.txt`.
2. Check out the code provided.

## Deploy To A Free Cloud Server (Heroku)

##TO BE CONTINUED
