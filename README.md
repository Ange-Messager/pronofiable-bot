import telebot, os
TOKEN=os.getenv("BOT_TOKEN")
bot=telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def start(m):
    bot.send_message(m.chat.id, "🔥 BIENVENUE PRONOFIABLE BOT 🤖\n\n/vip - Offre VIP\n/clasico - Barca vs Real\n/prono - Prono du jour\n/combine - Combine du jour 2.09")

@bot.message_handler(commands=['vip'])
def vip(m):
    bot.send_photo(m.chat.id, open('vip.jpg','rb'), caption="💎 OFFRE VIP PRONOFIABLE\nAccès à TOUS les pronos IA ! 👉 @Pronofiable")

@bot.message_handler(commands=['clasico'])
def clasico(m):
    bot.send_photo(m.chat.id, open('buts.jpg','rb'), caption="⚽ EL CLASICO - Scores exacts dans le VIP 👑")

@bot.message_handler(commands=['prono'])
def prono(m):
    bot.send_message(m.chat.id, "🤖 IA PRONOFIABLE :\n✅ Real ou Nul\n✅ BTTS\n✅ Over 2.5 buts")

@bot.message_handler(commands=['combine'])
def combine(m):
    bot.send_photo(m.chat.id, open('combine.jpg','rb'), caption="🔥 COMBINE DU JOUR - COTE 2.09\n✅ Analyse IA 100% validée\nRejoins le VIP 👑 @Pronofiable")

print("Bot lance...")
bot.infinity_polling()
