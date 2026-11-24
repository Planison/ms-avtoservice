# Мс-автосервис — сайт-визитка

Одностраничный сайт автосервиса и шиномонтажа в Янино-1 (Ленинградская область).
Один файл `index.html`: HTML + CSS + JS внутри, без библиотек, CDN и внешних шрифтов.

- Адрес: Ленинградская обл., Всеволожский р-н, г.п. Янино-1, Шоссейная ул., 66/1
- Телефон: +7 (921) 330-90-45
- Telegram: https://t.me/mcautoyanino
- Онлайн-запись: https://max.ru/u/f9LHodD0cOL5BXAP4_cr7CuknsbvN1colNvHNpA65gsgehSXGjpOoQXSo5g
- Яндекс Карты: https://yandex.ru/maps/org/ms_avtoservis/117976963302

## Публикация на GitHub Pages

### Вариант 1 — через этот репозиторий (Actions)

1. Создайте репозиторий на GitHub, например `ms-avtoservice`.
2. Залейте содержимое этой папки в ветку `main`.
3. В репозитории: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
4. Workflow `.github/workflows/deploy.yml` опубликует сайт при каждом push в `main`.
   Адрес: `https://<логин>.github.io/ms-avtoservice/`

### Вариант 2 — через интерфейс GitHub (без Actions)

**Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)`**.

### Свой домен

**Settings → Pages → Custom domain**, затем добавьте в DNS запись:
тип `CNAME`, имя — домен, значение — `<логин>.github.io`.
После включения домена замените `canonical` и `og:url` в `index.html` на реальный адрес.

## Что заменить перед запуском

- **Фото** — заглушки `.photo` в Hero и `.map-placeholder` в контактах. При замене на картинки
  добавьте `alt` и сжимайте в WebP (до ~200 КБ).
- **Точный график работы** — сейчас «Ежедневно до 21:00» в шапке, Hero, контактах, футере
  и в JSON-LD (`openingHours`). В коде это отмечено комментарием у блока «Часы работы».
- **Адрес сайта** — `canonical` и `og:url` в `<head>`.
- **Форма** — отправка имитируется (сообщение «Заявка принята» без бэкенда). Для реальных заявок
  подключите Formspree, Getform, Telegram Bot API через Cloudflare Worker или собственный обработчик.