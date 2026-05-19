# Задание 2: Проектирование API

## Часть 1: Пример REST API запроса

**Endpoint:** `GET /api/v1/partner-shops`

**Headers:**
- Authorization: Bearer token
- Accept-Language: ru

**Пример запроса:**
https://api.petrushka.ru/v1/partner-shops?lat=55.751244&lon=37.618423

## Часть 2: Пример ответа JSON

{
  "shops": [
    {
      "id": "shop_123",
      "name": "Магазин у дома №5",
      "address": "ул. Ленина, 15",
      "distance_km": 1.2,
      "rating": 4.7,
      "external_url": "https://partner-shop.ru",
      "work_hours": "09:00-21:00"
    },
    {
      "id": "shop_456",
      "name": "Супермаркет Ромашка",
      "address": "пр. Мира, 88",
      "distance_km": 2.5,
      "rating": 4.2,
      "external_url": "https://romashka.ru",
      "work_hours": "08:00-23:00"
    }
  ]
}

## Примечание
При клике на плашку магазина открывается external_url