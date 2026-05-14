# BBC News Telegram Bot

Бот для автоматического парсинга новостей BBC и отправки их в Telegram.

## Как работает

1. Каждые 5 секунд (можно изменить) бот забирает RSS-ленту BBC News
2. Парсит заголовки и ссылки на статьи
3. Отправляет свежие новости в Telegram

## Технологии

- n8n (платформа автоматизации)
- Telegram Bot API
- RSS BBC (https://feeds.bbci.co.uk/news/rss.xml)

## Установка

### 1. Запусти n8n

```bash
docker run -d --name n8n -p 5678:5678 -v ~/.n8n:/home/node/.n8n n8nio/n8n
```

### 2. Открой n8n

Перейди по адресу `http://localhost:5678`

### 3. Импортируй workflow

- Нажми "Import from File"
- Загрузи файл `BBC-News-Telegram-Bot.json`

### 4. Настрой Telegram

- Создай бота у [@BotFather](https://t.me/BotFather)
- Получи токен
- В ноде Telegram вставь токен и свой Chat ID

### 5. Запусти

Нажми "Publish" в n8n

## Структура

```
BBC-News-Telegram-Bot/
├── BBC-News-Telegram-Bot.json   # экспорт workflow
└── README.md
```

## Пример сообщения

```
📰 НОВОСТИ BBC

1. Four key excerpts from Streeting's resignation letter
   https://www.bbc.com/news/articles/c626wvqy1yzo

2. At a glance: Starmer fights to stay on as prime minister
   https://www.bbc.com/news/articles/c8jv1mzzkjgo

3. UK economy sees surprising growth
   https://www.bbc.com/news/articles/clyprjddgj3o

✅ Найдено новостей: 12
```

## Автор

[@ТВОЙ_ЮЗЕРНЕЙМ](https://github.com/ТВОЙ_ЮЗЕРНЕЙМ)

## Лицензия

MIT
