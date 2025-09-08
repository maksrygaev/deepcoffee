
# DeepCoffeeBot ☕

[![CI](https://github.com/твой-username/deepcoffee/actions/workflows/ci.yml/badge.svg)](https://github.com/твой-username/deepcoffee/actions)
[![Node.js](https://img.shields.io/badge/Node.js-20-blue?logo=node.js)](https://nodejs.org/)
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red)](#-лицензия)

**DeepCoffee Bot** — интеллектуальный Telegram бот на Node.js и TypeScript, использующий `grammy` и OpenAI для интерактивного общения. Redis хранит сессии пользователей. Полностью готов к CI/CD и продакшен-развёртыванию.  

---

## 🎥 Демо

![DeepCoffee Bot Demo](https://media.giphy.com/media/3o6ZtpxSZbQRRnwCKQ/giphy.gif)  
*(пример работы бота: отвечает на запросы и генерирует AI-ответы)*

---

## 📝 Особенности проекта

- ✅ Написан на **TypeScript** с ES Modules (`import/export`)  
- ✅ Telegram bot на **grammy**  
- ✅ Интеграция с **OpenAI API**  
- ✅ Хранение сессий/данных в **Redis**  
- ✅ CI/CD через GitHub Actions  
- ✅ Dev/Prod режимы без разделения env-файлов  
- ✅ Лёгкий деплой через PM2  
- ✅ Поддержка масштабирования и будущей контейнеризации через Docker  

---

## 📁 Структура проекта

deepcoffee/
├─ src/                  # Исходный код TypeScript
│  ├─ index.ts           # Точка входа бота
│  └─ bot.ts             # Основной код Telegram бота
├─ dist/                 # Скомпилированный JS (игнорируется git)
├─ node_modules/         # Зависимости
├─ package.json
├─ tsconfig.json
├─ .gitignore
├─ README.md
├─ .github/workflows/    # CI/CD workflow для GitHub Actions
│  └─ ci.yml

---

## ⚡ Требования

- Node.js >= 20  
- npm >= 9  
- Redis (локально или удалённо)  
- Telegram Bot Token (от BotFather)  
- OpenAI API Key  

---

## 🚀 Установка и запуск локально

1. Клонируем репозиторий:

```bash
git clone https://github.com/твой-username/deepcoffee.git
cd deepcoffee

	2.	Устанавливаем зависимости:

npm ci

	3.	Создаём .env файл с ключами:

TELEGRAM_BOT_TOKEN=ваш_токен_бота
OPENAI_API_KEY=ваш_api_key
REDIS_URL=redis://localhost:6379

	4.	Dev режим (авто-перезапуск при изменениях):

npm run dev

	5.	Продакшн:

npm run build
npm start


⸻

🛠 CI/CD через GitHub Actions
	•	При пуше в ветку main автоматически:
	1.	Клонируется репозиторий
	2.	Устанавливается Node.js
	3.	Скачиваются зависимости (npm ci)
	4.	Компилируется TypeScript (npm run build)
	5.	Запускаются тесты (если будут)
	•	Workflow файл: .github/workflows/ci.yml

⸻

💻 Продакшн-развёртывание

Вариант без Docker:
	1.	Устанавливаем Node.js на сервер
	2.	Копируем проект (git clone или scp)
	3.	Устанавливаем зависимости:

npm ci

	4.	Собираем проект:

npm run build

	5.	Запускаем через PM2:

pm2 start dist/index.js --name deepcoffee-bot
pm2 save
pm2 startup

Бот будет работать 24/7 и перезапускаться при падении.

⸻

📦 Будущие улучшения
	•	Добавить Docker для лёгкого деплоя и масштабирования
	•	Полноценные unit/integration тесты
	•	Telegram Mini Apps / вебхуки
	•	Расширение AI-функционала (репетитор, генератор контента)
	•	Возможность CI/CD деплоя в один клик

⸻

📜 Лицензия

All Rights Reserved © 2025 Макс
Unauthorized copying, modification or distribution prohibited.

