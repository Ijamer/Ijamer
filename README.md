import pyttsx3

while True:
    a = input("Введите текст:")
    if a == "Привет":
        engine = pyttsx3.init()
        engine.say("Привет")
        engine.runAndWait()
    elif a == "Как дела?":
        engine = pyttsx3.init()
        engine.say("Хорошо")
        engine.runAndWait()
        a2 = input("Как у вас дела?")
    elif a == "Пока":
        engine = pyttsx3.init()
        engine.say("До встречи")
        engine.runAndWait()
    elif a == "Кто написал Сталин Гулаг?":
        engine = pyttsx3.init()
        engine.say("Александр Валерьевич Горбунов")
        engine.runAndWait()
    elif a == "Кто ты?":
        engine = pyttsx3.init()
        engine.say("Я Степан, твой сосед")
        engine.runAndWait()
    elif a == "Ты робот?":
        engine = pyttsx3.init()
        engine.say("Как ты мог такое про меня сказать?")
        engine.runAndWait()
    else:
        engine = pyttsx3.init()
        engine.say("Пиши нормально, ничё не понимаю")
        engine.runAndWait()
