# 🌅 Закатник (Sunset Bot) - [@SunsetTGBot](https://web.telegram.org/k/#@SunsetTGBot)

[![Java](https://img.shields.io/badge/Java-17%2B-orange?style=flat-square&logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![Telegram API](https://img.shields.io/badge/Telegram-LongPollingBot-blue?style=flat-square&logo=telegram&logoColor=white)](https://core.telegram.org/bots/api)
[![SQLite](https://img.shields.io/badge/Database-SQLite-lightgrey?style=flat-square&logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)]()

*Умный Telegram-бот, который рассчитывает шанс на великолепный закат на основе метеопараметров, типов облачности и прогнозов погоды. Просто копируйте юз/переходите по ссылке и пользуйтесь.*

[English](#-english) • [Русский](#-русский)

</div>

---

## 🇺🇸 English

### 🎙 Backstory
This project was born purely out of a random moment: my best friend sent a voice message complaining that there was no simple app or program to check whether tonight's sunset was actually going to be breathtaking. I thought: *well, why the hell not?* — and built **Sunset Bot** ("Закатник").

### 🧠 Core Architecture & Features
Despite its casual origin, the bot features a robust backend architecture built with **Java** and **TelegramBots API**:
- **Smart Sunset Scoring Algorithm (`calculateSunsetChance`):** Evaluates wind speed, humidity, total cloudiness, and specific cloud types to calculate a 0–100% probability score for a stunning sunset.
- **Meteorological Cloud Classification (`identifyCloudType`):** Automatically maps raw weather description strings from OpenWeatherMap into concrete meteorological cloud formations (Stratus, Cumulus, Cirrus, Thunderstorms, etc.).
- **TimeZone & Location Sync:** Resolves exact geographic coordinates via Nominatim and calculates precise local sunset times using TimeZoneDB.
- **Automated Scheduling (`ScheduledExecutorService`):** Background scheduler triggers daily evening updates and alerts for users who opt-in to notifications.
- **Persistent Storage (SQLite):** Manages user city bindings, notification preferences, and interactive states (`UserCities` & `UserSettings` tables).
- **Admin Toolkit:** Built-in broadcast messaging (`/broadcast`), database cleaning (`/clean`), user statistics with Telegram `@username` resolution via Telegram API (`GetChat`), and input validation.

---

## 🇷🇺 Русский

### 🎙 Предыстория
Этот проект появился на свет максимально жизненно. Моя лучшая подруга записала голосовое, в котором эмоционально жаловалась на отсутствие нормальной программы, где четко и понятно показывались бы реальные шансы на шикарный закат. Я подумал: *«Ну почему бы нет?»* — и написал **«Закатник»**.

### 🧠 Архитектура и возможности
За шутливой концепцией скрывается полноценный бэкенд на **Java** с серьезным набором инженерных фич:
- **Интеллектуальный расчет шансов (`calculateSunsetChance`):** Комплексная система оценки, которая анализирует скорость ветра, влажность, процент облачности и тип туч, выдавая итоговый вердикт с уникальным настроением.
- **Метеорологический парсер облаков (`identifyCloudType`):** Переводит сухие системные описания OpenWeatherMap в понятные типы (перистые, кучевые, слоисто-дождевые, грозовые тучи и т.д.).
- **Работа с часовыми поясами:** Динамическое определение координат и точного времени заката под локацию пользователя через TimeZoneDB и OpenWeatherMap.
- **Фоновый планировщик (`ScheduledExecutorService`):** Автоматически рассчитывает задержку до вечернего времени (16:00 и 19:30) и запускает ежедневную рассылку напоминаний тем, у кого включены уведомления.
- **База данных SQLite (`SQLiteDataSource`):** Надежное хранение привязок пользователей к городам и их индивидуальных настроек уведомлений.
- **Админ-панель:** Инструменты для массовой рассылки сообщений (`/broadcast`), просмотра статистики по пользователям с подтягиванием их `@username` через Telegram API (`GetChat`), очистки базы и защиты от неверного ввода.

---
