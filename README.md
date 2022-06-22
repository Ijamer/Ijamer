import telebot
from telebot import types
# Создаем экземпляр бота
bot = telebot.TeleBot('5570839078:AAHFgXF6JG1A7f4hm-Qe8P54H7VBaGTxbF8')
# Функция, обрабатывающая команду /start
@bot.message_handler(commands=["start"])
def start(m, res=False):
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    item1 = types.KeyboardButton("Кто ты?")
    item2 = types.KeyboardButton("О чём ты можешь рассказать?")
    markup.add(item1)
    markup.add(item2)
    bot.send_message(m.chat.id, '\nКто ты?\nО ты чём можешь рассказать? ',  reply_markup=markup)
# Получение сообщений от юзера
@bot.message_handler(content_types=["text"])
def handle_text(message):
    # Если юзер прислал 1, выдаем ему случайный факт
    if message.text == 'Кто ты?':
        bot.send_message(message.chat.id, "Я бот написанный 8-ми классником, призваный помогать людям в обучении компьютерных игр.")
    # Если юзер прислал 2, выдаем умную мысль
    elif message.text == 'О чём ты можешь рассказать?':
        bot.send_message(message.chat.id, "Я могу рассказать вам о: VALORANT, CS:GO, APEX LEGENDS")
        markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
        item1 = types.KeyboardButton("VALORANT")
        item2 = types.KeyboardButton("CS:GO")
        item3 = types.KeyboardButton("APEX LEGENDS")
        markup.add(item1)
        markup.add(item2)
        markup.add(item3)
        @bot.message_handler(content_types=["text"])
        def handle_text(message):
            if message.text == 'VALORANT':
                bot.send_message(message.chat.id, "На ком ты играешь?")



bot.polling(none_stop=True, interval=0)
