const { Client, GatewayIntentBits } = require('discord.js');

const client = new Client({
  intents: [
    GatewayIntentBits.Guilds,
    GatewayIntentBits.GuildMessages,
    GatewayIntentBits.MessageContent
  ]
});

client.once('ready', () => {
  console.log(`${client.user.tag} is online!`);
});

client.on('messageCreate', message => {

  if (message.author.bot) return;

  const msg = message.content.toLowerCase();

  if (msg === 'hi') {
    message.reply('Hello 👋');
  }

  if (msg === 'minecraft') {
    message.reply('Minecraft is Awesome ⛏️');
  }

});

client.login(process.env.MTQzOTMwNjc2NTgxNTY0ODQ2MA.G92vpl._aBhGES-dSHL5f-EKDEH63p4A1_e_AYwsvaGUQ);
