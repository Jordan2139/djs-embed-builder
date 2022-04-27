<h1 align="center">hyperz-djs-embed-builder</h1>

### This was originally created by PlutoTheDev
### This was modified to support DarkBot Multi-Language Functionality

## Usage
```js
const language = require('./en-us.json');
const { Client } = require('discord.js');
const djs = require(`hyperz-djs-embed-builder`);
const client = new Client();
client.embed = new djs(client).createEmbed

client.on("interactionCreate", (client, interaction) => {
    if (interaction.commandName == "embed") {
        client.embed(interaction, language);
    };
});

client.on("messageCreate", (client, message) => {
    let prefix = "+";
    let args = message.content.slice(prefix.length).trim().split(/ +/g);
    let command = args.shift().toLowerCase();
    if (command == "embed") {
        client.embed(message, language);
    };
});
```


## Dependencies 
* [Discord.js@13.6.0](https://npmjs.com/package/discord.js)
