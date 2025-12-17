# Лабораторная работа 16: ML Web Apps на Julia


## Быстрый старт

## 🪟 Для Windows пользователей

### Используйте .bat файлы:

1. **Установка:** `install.bat`
2. **Обучение:** `train.bat` 
3. **Запуск:** `run.bat`
4. **Тестирование:** `test.bat`
5. **Всё сразу:** `all.bat`

### Или команды вручную:

:: 1. Установить зависимости
```
julia --project=. setup.jl
```
:: 2. Обучить модель
```
julia --project=. simple_model_fixed.jl
```
:: 3. Запустить сервер
```
julia --project=. working_final_api.jl
```
:: 4. Тестировать (в другом окне cmd)
```
curl http://localhost:8080/health
curl -X POST http://localhost:8080/predict -H "Content-Type: application/json" -d "{\"features\": [0.5, 0.3, 0.8]}"
```
Или используйте Makefile:
# Установить всё и запустить
```
make all
```
# Только тестирование
```
make test
```
# Python сравнение
```
make compare
```
Файлы проекта
working_final_api.jl - Основной API сервер

simple_model_fixed.jl - Обучение ML модели

decision_tree_model.jls - Сохраненная модель (96.7% точность)

test_client.jl - Тестовый клиент

app.py - Python аналог для сравнения

API_EXAMPLES.md - Примеры использования API
API эндпоинты
GET / - Веб-интерфейс

GET /health - Проверка здоровья

POST /predict - Предсказание класса
```
curl -X POST http://localhost:8080/predict \\
  -H "Content-Type: application/json" \\
  -d '{"features": [0.5, 0.3, 0.8]}'
```
```
{
  "success": true,
  "prediction": 0,
  "features": [0.5, 0.3, 0.8],
  "timestamp": "2025-12-03T20:15:35.456"
}
```
Технологии
Julia 1.8.5 - основной язык

DecisionTree.jl - алгоритм машинного обучения

HTTP.jl - веб-сервер

JSON3.jl - обработка JSON

Flask (Python) - для сравнения производительности

Результаты
✅ ML модель с точностью 96.7%

✅ Рабочий REST API сервер

✅ Интерактивный веб-интерфейс

✅ Полная документация

✅ Python аналог для сравнения

© 2025 Лабораторная работа по разработке интерфейсов для ML, Любимый Дмитрий МИК22
