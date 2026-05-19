# Задание 2: Проектирование API

## Часть 1: Пример REST API запроса

GET /api/v1/partner-shops

Headers:
- Authorization: Bearer token
- Accept-Language: ru

## Часть 2: Пример ответа REST API (JSON)

{
  "shops": [
    {
      "id": "1",
      "name": "Магазин у дома",
      "address": "ул. Ленина, 15",
      "distance_km": 1.2,
      "rating": 4.7,
      "external_url": "https://example.com/shop1",
      "work_hours": "09:00-21:00"
    },
    {
      "id": "2",
      "name": "Супермаркет Ромашка",
      "address": "пр. Мира, 88",
      "distance_km": 2.5,
      "rating": 4.2,
      "external_url": "https://example.com/shop2",
      "work_hours": "08:00-23:00"
    }
  ]
}

## Описание полей

| Поле | Тип | Описание |
|------|-----|----------|
| id | string | ID магазина |
| name | string | Название |
| address | string | Адрес |
| distance_km | float | Расстояние в км |
| rating | float | Рейтинг 0-5 |
| external_url | string | Ссылка для перехода |
| work_hours | string | Часы работы |

## Примечание

При клике на плашку магазина открывается external_url.

## Ошибка авторизации

{
  "status": "error",
  "code": 401,
  "message": "Недействительный токен"
}
