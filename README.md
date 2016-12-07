# Botanalytics Middleware for Microsoft Bot Framework

[Botanalytics](https://botanalytics.co) is an conversational analytics&engagement tool for bots.


## Installation

Add `botanalytics-microsoftbotframework-middleware` to your `package.json`

```
$ npm install botanalytics-microsoftbotframework-middleware
```

## Usage

Register your bot with
[Botanalytics](https://botanalytics.co). Once you registered, please find your token at the integration page or navigate to Settings to see your token.

Set the following environment variable with the Token respectively.

```
BOTANALYTICS_TOKEN=your-botanalytics-token
```

Require `botanalytics-microsoftbotframework-middleware` and use the middleware in your bot like so:

```javascript
// Initialize the middleware
var BotanalyticsMiddleware = require('botanalytics-microsoftbotframework-middleware').BotanalyticsMiddleware({
  token: process.env.BOTANALYTICS_TOKEN
});

// Initialize the connector and the bot
var connector = new builder.ChatConnector({
    appId: process.env.MICROSOFT_APP_ID,
    appPassword: process.env.MICROSOFT_APP_PASSWORD
});
var bot = new builder.UniversalBot(connector);

// Use the middleware
bot.use(
  {
    receive: BotanalyticsMiddleware.receive,
    send: BotanalyticsMiddleware.send
  }
);
```

## License

[MIT License](http://opensource.org/licenses/MIT).
