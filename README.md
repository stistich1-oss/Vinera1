# 🎰 VINERA Telegram Slot Casino

Встроенный слот-казино для Telegram с Mini App и управлением балансом через Python-бэкенд.

## 📋 Структура проекта

```
vinera-bot/
├── bot.py                      # Основной Telegram бот (aiogram)
├── api.py                      # FastAPI сервер (слот API)
├── database.py                 # SQLite управление
├── config.py                   # Конфигурация
├── slot_engine.py              # RNG генератор спинов
├── requirements.txt            # Python зависимости
├── .env                        # Переменные окружения (НЕ коммитить!)
├── Dockerfile                  # Для контейнеризации
├── docker-compose.yml          # Для локального запуска
├── database.db                 # SQLite БД (создаётся автоматически)
└── static/
    └── slot/
        ├── index.html          # Главная страница WebApp
        ├── css/
        │   └── slot.css        # Стили (тёмная тема)
        └── js/
            └── slot.js         # Логика слота (Telegram WebApp)
```

## 🚀 Быстрый старт

### 1. Установка

```bash
git clone https://github.com/stistich1-oss/Vinera1.git
cd Vinera1
pip install -r requirements.txt
echo "BOT_TOKEN=YOUR_BOT_TOKEN" > .env
echo "WEBAPP_URL=http://localhost:8000" >> .env
```

### 2. Запуск (2 терминала)

**Terminal 1:**
```bash
python api.py
```

**Terminal 2:**
```bash
python bot.py
```

## 🎮 Особенности

- ✅ Слот с 3 барабанами (5 символов)
- ✅ RNG на сервере (почти 95% RTP)
- ✅ Telegram Mini App (полноэкранный)
- ✅ Автоматическая авторизация (initData)
- ✅ Управление балансом (SQLite)
- ✅ Тёмная тема (#0d0d0d)
- ✅ Анимация 1.5 сек

## 📊 Таблица выплат

| Комбинация | x |
|-----------|---|
| 💎💎💎   | 50 |
| 7️⃣7️⃣7️⃣   | 20 |
| ⭐⭐⭐    | 10 |
| 🍒🍒🍒   | 5  |
| 🍋🍋🍋   | 2  |

## 🔗 API

### POST /api/init
```json
{"init_data": "user%3D..."}
```

### POST /api/spin
```json
{"user_id": 123, "bet_amount": 10}
```

## 📝 Версия: 1.0.0
