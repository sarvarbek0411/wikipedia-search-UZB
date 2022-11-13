# wikipedia-search-UZB
import telebot
import wikipedia
wikipedia.set_lang("uz")
bot=telebot.TeleBot("5656065499:AAHFQYr-vHngL1AKgx5g6lqasgJQsP455bk")
@bot.message_handler(commands=['start'])
def start(message):
    bot.send_message(message.chat.id, '🇺🇿 Assalomu alaykum bizning https://t.me/Wikipedia_search_UZB_bot 👈👈👈imizga xush kelibsiz Bu botda siz wikipediadan qidirgan🔍 narsangizni topasiz😎😎')
@bot.message_handler(content_types=["text"])
def text(message):
    final=message.text
    try:
        mess=wikipedia.summary(final)

        bot.send_message(message.chat.id, mess)



    except:
        bot.send_message(message.chat.id, "Bunday ma'lumot topilmadi")

bot.polling()
