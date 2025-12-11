[Untitled-1.js](https://github.com/user-attachments/files/24106782/Untitled-1.js)
// Import Discord.js v14
const { Client, GatewayIntentBits, Partials, ActionRowBuilder, ButtonBuilder, ButtonStyle, Events } = require('discord.js');
const client = new Client({
    intents: [
        GatewayIntentBits.Guilds,
        GatewayIntentBits.GuildMembers,
        GatewayIntentBits.GuildMessages,
        GatewayIntentBits.MessageContent
    ],
    partials: [Partials.Channel]
});

// CONFIGURAȚIE
const GUILD_ID = '1413937276827734140';        // Înlocuiește cu ID-ul serverului tău
const VIP_ROLE_ID = '1428766311999082566';    // Înlocuiește cu ID-ul rolului VIP
const PREFIX = ',';                  // Prefix comenzi

// Când botul pornește
client.once(Events.ClientReady, () => {
    console.log('ZeMoFox este online și gata de acțiune! 🌹');
});

// Comandă verificare
client.on(Events.MessageCreate, async (message) => {
    if (message.author.bot) return;

    if (message.content.toLowerCase() === `${PREFIX}verificare`) {
        const row = new ActionRowBuilder()
            .addComponents(
                new ButtonBuilder()
                    .setCustomId('verificat')
                    .setLabel('✅ Verifică-mă')
                    .setStyle(ButtonStyle.Success)
            );

        await message.channel.send({
            content: `🌹 **Bine ai venit în Lounge-ul VIP**
