# Календарь встреч (Calendar Booking API)

Fullstack-приложение бронирования встреч: гость выбирает тип события и
свободный слот и записывается, владелец создаёт типы событий и управляет
бронированиями.

## Архитектура

| Каталог    | Назначение                                                    |
| ---------- | ------------------------------------------------------------- |
| `api-spec` | Контракт API (TypeSpec → OpenAPI), определяет все эндпоинты   |
| `server`   | Бэкенд по контракту: Node.js + TypeScript, хранилище в памяти |
| `web`      | Фронтенд (React + Vite), работает с API только по контракту   |

Бэкенд предоставляет публичное API гостя (`/guest/*`) и админское API
владельца (`/admin/*`). В dev-режиме Vite проксирует эти пути на бэкенд
(`http://localhost:8080`).

## Запуск

```bash
# 1. Бэкенд (порт 8080)
cd server
npm install
npm start

# 2. Фронтенд (порт 5173), в другом терминале
cd web
npm install
npm run dev
```

Откройте http://localhost:5173 — вкладки «Гость» и «Владелец».

> Бэкенд хранит данные в памяти: после перезапуска сервиса бронирования и
> созданные типы событий сбрасываются в демонстрационные.

## Status

[![Actions Status](https://github.com/FoxxMGR/fullstack-javascript-project-386/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/FoxxMGR/fullstack-javascript-project-386/actions)