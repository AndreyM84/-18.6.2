# 18.6.2
Ошибки отмечены #.......(комментарии)
# Файл config.py
token = '1493436800:AAF1Eult9X13lyLQGGdScK63MbGOJyGqGbk'

keys = {
    'евро': 'EUR',
    'доллар': 'ЮэСДэ', 
    # Не верное обозначение валюты (USD)
    'рубль': 'RUB',    
  }
  
  # Файл app.py 
  
   @bot.message_handler(commands=['help'])
def help(message: telebot.types.Message):
    text = 'Чтобы начать конвертацию, введите команду боту в следующем формате: \n<имя валюты> <в какую валюту перевести> <количество переводимой валюты>\nЧтобы увидеть список всех доступных валют, введите команду\n/values' 
    # ошибка в написании кода \n/values. Корректное написание:<количество переводимой валюты>\nУвидеть список всех доступных валют: /values'
    
    bot.reply_to(message, text) 
    
    # Файл extensions.py 
    
import json
import requests
from config import * # Нужно импортировать keys вместо *
*
*
*
 r = requests.get(
            f'https://min-api.cryptocompare.com/data/price?fsym={base_ticker}&tsyms={quote_ticker}') # Ошибка кода - пишется в одну строку
        total_base = float(json.loads(r.content)[keys[quote]])
        return total_base
