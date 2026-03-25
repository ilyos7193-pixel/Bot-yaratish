import telebot

TOKEN = "8796086416:AAHYmSJdUkMTwhzvTdiij6Nk5uKMCNt5T4g"  # BotFather dan olgan tokening

bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def start(message):
    bot.send_message(message.chat.id, "Salom! Bot ishlayapti ✅")

@bot.message_handler(func=lambda message: True)
def echo(message):
    # Foydalanuvchining yozganini qaytaradi
    bot.send_message(message.chat.id, message.text)

bot.infinity_polling()
