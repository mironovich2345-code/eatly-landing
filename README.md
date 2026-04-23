# EATLY Landing Page

Статический лендинг для продукта [EATLY](https://t.me/EATLYY_bot) — бота и мини-приложения для контроля питания.

## Структура

```
index.html      — весь лендинг, один файл, без зависимостей
wrangler.toml   — конфиг для деплоя на Cloudflare Pages
README.md       — этот файл
```

## Открыть локально

Просто открой `index.html` в браузере — никаких сборщиков и серверов не нужно.

```bash
open index.html
# или
python3 -m http.server 8080
```

## Деплой на Cloudflare Pages

### Вариант 1 — через дашборд (рекомендуется)

1. Залей репозиторий на GitHub
2. Открой [Cloudflare Pages](https://pages.cloudflare.com/)
3. Нажми **Create a project → Connect to Git**
4. Выбери репозиторий `eatly-landing`
5. Настройки сборки:
   - **Build command:** *(оставить пустым)*
   - **Output directory:** `/` или `.`
6. Нажми **Save and Deploy**

### Вариант 2 — через CLI

```bash
npm install -g wrangler
npx wrangler pages deploy . --project-name=eatly-landing
```

## Что нужно заменить вручную

Все ссылки на продукт сосредоточены в `index.html`. Найти по комментарию `CONSTANTS` в начале файла.

| Место | Текущее значение | Что заменить |
|---|---|---|
| CTA-кнопки (приложение/бот) | `https://t.me/EATLYY_bot` | актуальная ссылка на бот |
| Кнопка «Стать экспертом» | `href="#"` | ссылка на форму/бот для экспертов |
| Политика конфиденциальности | `href="#"` | реальный URL документа |
| Условия использования | `href="#"` | реальный URL документа |
| Контакты | `href="#"` | email или ссылка |

## Технические детали

- Чистый HTML/CSS/JS, без фреймворков и зависимостей
- Шрифт Plus Jakarta Sans загружается с Google Fonts
- Мобильная адаптация встроена
- Работает на любом статическом хостинге: Cloudflare Pages, Netlify, Vercel, GitHub Pages
