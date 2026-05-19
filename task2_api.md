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
      "name": "METRO",
      "delivery_info": "Ближайшая доставка сегодня 21:00–23:00",
      "external_url": "https://metro.ru/petrushka"
    },
    {
      "id": "2",
      "name": "Ашан",
      "delivery_info": "Ближайшая доставка сегодня 18:00–20:00",
      "external_url": "https://ashan.ru/petrushka"
    },
    {
      "id": "3",
      "name": "ВкусВилл",
      "delivery_info": "Быстрая доставка от 20 до 60 минут",
      "external_url": "https://vkusvill.ru/petrushka"
    },
    {
      "id": "4",
      "name": "ВИКТОРИЯ",
      "delivery_info": "Ближайшая доставка сегодня 17:00–19:00",
      "external_url": "https://victoria.ru/petrushka"
    }
  ]
}

## Описание полей

| Поле | Тип | Описание |
|------|-----|----------|
| id | string | Уникальный идентификатор магазина |
| name | string | Название магазина (METRO, Ашан и т.д.) |
| delivery_info | string | Информация о доставке (из макета) |
| external_url | string | Ссылка на внешний ресурс (открывается при клике) |

## Примечание

При клике на плашку магазина открывается external_url во внешнем браузере или WebView.

## Пример ответа при ошибке

{
  "status": "error",
  "code": 401,
  "message": "Недействительный токен авторизации"
}
