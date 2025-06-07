# LuskyWinBot-
Telegram псевдо-сигнал бот для игры Lusky Jet и 1Win
import telebot

TOKEN = '8072739820:AAHFeuteNxa3J3Wak9B_QG-j3FFOrYJmDa8'

bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def send_welcome(message):
    bot.reply_to(message, "Привет! Это LuskyWinBot, твой помощник по Lusky Jet.")

@bot.message_handler(commands=['signal'])
def send_signal(message):
    bot.reply_to(message, "Сигнал для Lusky Jet: старт!")

@bot.message_handler(func=lambda message: True)
def echo_all(message):
    bot.reply_to(message, "Извини, я пока не понимаю это сообщение.")

bot.polling()
