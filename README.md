# Buildo Бизнес-аватары — Telegram-бот

> **Профессиональные AI-портреты для резюме и LinkedIn за 2 минуты**

Часть экосистемы **Buildo** (https://buildo.ru). MIT licensed. Open source.

![Buildo](https://img.shields.io/badge/Buildo-ecosystem-5B8DEF?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)

---

## Что это

Telegram-бот для продукта Бизнес-аватары. Сервисный слой: вход в Mini App, оплата, ingestion, уведомления.

**Сценарий использования (Telegram-бот):** Отправь 3-5 своих фото → получи пакет аватаров

---

## Архитектура

```
Buildo Бизнес-аватары экосистема
├── shekelstrong/buildo-headshots-tg          ← этот репо (Telegram-бот)
├── shekelstrong/buildo-headshots-miniapp    ← Mini App
└── shekelstrong/buildo-headshots-site        ← Маркетинговый сайт
```

---

## Стек

| Слой | Технология |
|---|---|
| Bot | aiogram 3.x + Redis FSM + Docker |
| Frontend | Vite + React 19 + Tailwind + Telegram WebApp SDK |
| Backend | FastAPI + SQLAlchemy Async + OpenRouter/YandexART + ЮKassa |
| AI (image) | YandexART (или OpenRouter vision для fallback) |
| AI (text) | OpenRouter/MiniMax M3 для prompt engineering |
| Deploy | VPS 108.165.164.85 / 31.76.29.244 через CI/CD (GitHub Actions → SSH) |

---

## Монетизация

990 ₽ за 10 фото / 2490 ₽ за 30 фото

**Целевая аудитория:** Фрилансеры, IT-специалисты, корпоративный найм
**Конкуренты (РФ):** HeadshotPro, Avatarize, фото-ателье (5-15 тыс ₽)

---

## Деплой

```bash
cp .env.example .env
# заполни: TELEGRAM_BOT_TOKEN, OPENROUTER_API_KEY, YOOKASSA_*
docker compose up --build
```

Продакшен:
```bash
git push origin main  # GitHub Actions → SSH → VPS → docker compose up -d --build
```

---

## Связанные репо

- [buildo-headshots-tg](https://github.com/shekelstrong/buildo-headshots-tg) — этот репо
- [buildo-headshots-miniapp](https://github.com/shekelstrong/buildo-headshots-miniapp)
- [buildo-headshots-site](https://github.com/shekelstrong/buildo-headshots-site)
- [nemo-team-docs/projects/buildo/headshots/](https://github.com/shekelstrong/nemo-team-docs/tree/main/projects/buildo/headshots) — спецификация

---

## License

MIT (c) 2026 Buildo Ecosystem. Inspired by [awesome-generative-ai-apps](https://github.com/Anil-matcha/awesome-generative-ai-apps).