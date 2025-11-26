# Monitoring System · Prometheus + Grafana + Node Exporter + Alertmanager

![Go](https://img.shields.io/badge/Go-1.23-00ADD8?logo=go&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Полноценная система мониторинга и алертинга на базе стека **Prometheus + Grafana + Alertmanager**, полностью контейнеризованная через **Docker Compose**.

## Особенности проекта

- Полностью готово к запуску одной командой
- Преднастроенные дашборды Grafana 
- Persistant хранилище для Prometheus и Grafana
- Чистая и понятная структура проекта
- Поддержка архитектур `linux/amd64` и `linux/arm64` (Apple Silicon)

## Стек

| Компонент          | Версия      | Описание                                   |
|--------------------|-------------|--------------------------------------------|
| Prometheus         | 2.54.1      | Сбор и хранение метрик                     |
| Grafana            | 12.3.0      | Визуализация и дашборды                    |

## Быстрый старт

```bash
# 1. Клонируем репозиторий
git clone https://github.com/vyacheslav-moiseev/monitoring.git
cd monitoring

# 2. Запускаем всё
docker compose up -d

# 3. Готово! Открываем дашборды


# Пересоздать всё с нуля
docker compose down -v && docker compose up --build -d

# Посмотреть логи конкретного сервиса
docker compose logs -f grafana

# Обновить только Prometheus
docker compose pull prometheus && docker compose up -d prometheus



## ТЗ

Мониторинг доступности сайта
В docker развернуть prometheus & grafana
Настроить мониторинг доменов (не чаще чем 1 раз в минуту): leads.su api.leads.su tracker.leads.su
Настроить графики в grafana
Сделать триггеры на недоступность
