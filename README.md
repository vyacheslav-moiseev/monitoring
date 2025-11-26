# Мониторинг: Prometheus + Grafana + Blackbox Exporter

Тестовое задание — развёртывание системы мониторинга с помощью Docker Compose.

Мониторинг доступности сайта
В docker развернуть prometheus & grafana
Настроить мониторинг доменов (не чаще чем 1 раз в минуту): leads.su api.leads.su tracker.leads.su
Настроить графики в grafana
Сделать триггеры на недоступность


Исправлено: 
Добвавлены Dashboards provisioning 

probe_success_full.json
Сделал полный дашборд для blackbox_exporter, который сразу покажет все три URL (leads.su, tracker.leads.su, api.leads.su) на одной панели с цветной индикацией успех/неуспех.
Что делает этот дашборд

Timeseries панель
-Показывает все три URL на одной временной линии.
-Цвет графика: зеленый = успех, красный = провал.
-Легенда с каждым URL.

Stat панель
-Показывает последнее состояние каждого URL как единичный виджет.
-Красный = упал, зеленый = работает.

probe_alerts.json
Grafana с provisioning поддерживает alerting через panel alerts. Для временных рядов (timeseries) можно настроить условие: если probe_success=0 больше N минут → триггер алерта.

Что делает этот дашборд

Timeseries панель для всех трёх URL.
-Алерт триггерится, если:
-probe_success=0 в течение последних 2 минут для любого URL.
-Цвет графиков и статусы отображаются автоматически (red = fail, green = success).

## Запуск

```bash
docker-compose up -d