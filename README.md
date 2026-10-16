# Буфало — сайт тату-студии

Адаптивный одностраничный сайт-портфолио вымышленной тату-мастерской «Буфало». Стиль вдохновлён страницами продуктов Apple: крупная типографика, много воздуха, стеклянные панели (glassmorphism) и плавные анимации. Сайт на русском и английском.

**Демо:** https://ВАШ-НИК.github.io/НАЗВАНИЕ-РЕПОЗИТОРИЯ/

<!-- Добавьте скриншот: ![Главный экран](screenshots/hero.png) -->

## Возможности

- Главный экран с названием, которое появляется по буквам, и параллаксом при прокрутке
- Галерея работ: плитки с плавным появлением, параллаксом фото и бликом за курсором
- Карточки мастеров с эффектом стекла и подсветкой под курсором
- Форма записи: собирает заявку, показывает готовый текст, копирует его в буфер и открывает письмо
- Переключатель языка RU / EN, выбор запоминается в браузере
- Светлая и тёмная тема автоматически, по настройкам системы
- Курсор-кольцо, притягивающиеся кнопки, полоса прогресса прокрутки, бегущий текст
- Учитывает `prefers-reduced-motion`: при включённом «уменьшить движение» анимации отключаются
- Адаптивная вёрстка для телефонов, планшетов и компьютеров

## Технологии

Чистые HTML, CSS и JavaScript, без фреймворков и сборки. Весь сайт лежит в одном файле `index.html`, фотографии встроены в него. Шрифт Inter подключается через Google Fonts.

## Запуск

Откройте `index.html` в браузере, больше ничего не нужно.

Для локального сервера:

```bash
python3 -m http.server 8000
# откройте http://localhost:8000
```


## Что заменить на свои данные

В `index.html` найдите и поправьте:

| Что | Где искать |
| --- | --- |
| Название, тексты, подписи | русские тексты в разметке и словарь `D` (английский) в конце файла |
| Мастера и их описания | блок `<div class="ms">` и словарь `D` |
| Телефон, Telegram, адрес, режим работы | секция `id="contacts"` |
| Почта для заявок | `hello@buffalo.example` в обработчике формы |
| Фото работ | теги `<img>` внутри `<figure class="tile">` (встроены как base64) |

## Важно про форму записи

Форма работает как демонстрация. Сайт статический, поэтому заявки никуда не отправляются автоматически: после нажатия клиент получает готовый текст, который можно скопировать или открыть в почтовой программе (адрес-заглушка).

Чтобы заявки приходили сами, подключите сервис форм, например Formspree, Web3Forms или Google Apps Script, либо бота в Telegram. Для этого в обработчике `f.onsubmit` нужно отправить данные через `fetch` на адрес сервиса.

## Фотографии

<img width="1886" height="741" alt="image" src="https://github.com/user-attachments/assets/c9f15032-09b6-43d6-b35c-cc332bc20718" />


## Структура

```
.
├── index.html   # весь сайт: разметка, стили и скрипты
└── README.md
```

## English

A responsive single-page portfolio site for a fictional tattoo studio, "Buffalo". It uses an Apple-style layout with glassmorphism panels, scroll-driven and hover animations, a RU/EN language switch and automatic light/dark themes. It is built with plain HTML, CSS and JavaScript in a single `index.html` file, with no build step. To deploy, push the file to a GitHub repository and enable GitHub Pages (Settings → Pages → Deploy from a branch). The booking form is a demo: it builds the request text and opens a mail draft, and needs a form service or backend to send requests automatically. Replace the sample photos and contact details with your own before publishing.

## Лицензия

Добавьте файл `LICENSE` по вашему выбору, например MIT.
