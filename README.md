# EATLYY Landing Page

AI-дневник питания в Telegram и MAX. Чистый статический лендинг — без фреймворков, без сборки.

## Структура

```
index.html          — лендинг (86 KB)
assets/
  screen-1.png      — главный экран приложения
  screen-2.png      — выбор граммов
  screen-3.png      — анализ готов (чипсы)
  screen-4.png      — статистика
README.md           — этот файл
```

## Деплой на Cloudflare Pages

### ✅ Правильный способ — через дашборд (только Pages, без Workers)

1. Залей репозиторий на GitHub
2. Открой [dash.cloudflare.com](https://dash.cloudflare.com) → **Рабочие страницы** → **Создать проект**
3. **Подключить к Git** → выбери репозиторий
4. Настройки сборки:

| Параметр | Значение |
|---|---|
| Framework preset | **None** |
| Build command | *(оставить пустым)* |
| Build output directory | *(оставить пустым или `/`)* |

5. **Сохранить и развернуть**

> ⚠️ `wrangler.toml` в репозитории не нужен и не должен присутствовать — он путает Cloudflare и вызывает ошибку деплоя.

### Почему раньше не работало

| Причина | Объяснение |
|---|---|
| `wrangler.toml` в репо | Cloudflare видит его и переключается в режим Workers deploy |
| Workers ищет `main` или `dist` | Этих файлов нет — проект статический |
| `[assets]` и `pages_build_output_dir` не помогают | Cloudflare Pages и Workers — разные системы |
| Решение | Удалить `wrangler.toml`, настроить через дашборд Pages |

## Локальный запуск

```bash
# Через локальный сервер (рекомендуется):
python3 -m http.server 8080
# → http://localhost:8080

# Или npx:
npx serve .
```

## Ссылки продукта

| Что | Значение |
|---|---|
| Telegram-бот | https://t.me/EATLYY_bot |
| MAX-бот | https://max.ru/id222516043000_bot |
| Email | info@eatlyy.ru |
