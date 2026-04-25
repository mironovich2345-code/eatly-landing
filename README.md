# EATLYY Landing Page

Лендинг для [EATLYY](https://t.me/EATLYY_bot) — AI-дневника питания в Telegram и MAX.

## Структура

```
index.html          — лендинг (86 KB, без зависимостей)
assets/
  screen-1.png      — главный экран приложения (hero)
  screen-2.png      — экран выбора граммов (AI demo)
  screen-3.png      — анализ готов — чипсы (AI demo)
  screen-4.png      — экран статистики
wrangler.toml       — конфиг для деплоя на Cloudflare Pages
README.md           — этот файл
```

## Локальный запуск

```bash
# Просто открой в браузере:
open index.html

# Или через локальный сервер (рекомендуется для корректной загрузки assets):
python3 -m http.server 8080
# → http://localhost:8080
```

> ⚠️ При открытии `index.html` напрямую (file://) изображения в `assets/` могут не загружаться из-за CORS. Используй локальный сервер.

## Деплой на Cloudflare Pages

### Вариант 1 — через дашборд (рекомендуется)

1. Залей репозиторий на GitHub
2. Открой [Cloudflare Pages](https://pages.cloudflare.com/)
3. **Create a project → Connect to Git**
4. Выбери репозиторий `eatlyy-landing`
5. Настройки сборки:
   - **Build command:** *(оставить пустым)*
   - **Output directory:** `/` или `.`
6. **Save and Deploy**

### Вариант 2 — через CLI

```bash
npm install -g wrangler
npx wrangler pages deploy . --project-name=eatlyy-landing
```

## Ссылки продукта

| Что | Значение |
|---|---|
| Telegram-бот | `https://t.me/EATLYY_bot` |
| MAX-бот | `https://max.ru/id222516043000_bot` |
| Email | `info@eatlyy.ru` |

## Что нужно заменить вручную

| Место в коде | Что заменить |
|---|---|
| `href="https://max.ru/id222516043000_bot"` | Проверить точный URL MAX-бота |
| `href="#"` у «Стать партнёром» | Реальная ссылка или форма |
| Политика конфиденциальности | Реальный URL документа |
| Условия использования | Реальный URL документа |

## Технические детали

- Чистый HTML/CSS/JS, без фреймворков
- Шрифт: Plus Jakarta Sans (Google Fonts)
- Изображения: `assets/` папка, PNG
- Адаптирован для мобильных
- Поддержка `prefers-reduced-motion`
- Деплоится на любой статический хостинг
