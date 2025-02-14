from telethon import TelegramClient, events

api_id = '20563008'
api_hash = 'cbf6595af9a1121bf61c15300320b962'
bot_token = '7926498816:AAHwJqUn2qN3IudwpeZRHdgKdco_H_nWemI'

client = TelegramClient('bot', api_id, api_hash).start(bot_token=bot_token)

@client.on(events.NewMessage)
async def echo_handler(event):
    await event.respond(event.message.message)

print("Bot started. Send him a message!")
client.run_until_disconnected()
