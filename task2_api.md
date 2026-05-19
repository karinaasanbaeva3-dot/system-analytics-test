# Задание 2: Проектирование API

## Часть 1: Пример REST API запроса

При переходе пользователя на экран "Магазины партнеров" вызывается запрос:

**Endpoint:**
GET /api/v1/partner-shops

**Headers:**
Authorization: Bearer <access_token>
Accept-Language: ru
Accept: application/json

**Query параметры (опционально, для сортировки по геопозиции):**
GET /api/v1/partner-shops?lat=55.751244&lon=37.618423&radius=5

**Параметры:**
- lat (number) - широта текущего местоположения (необязательный)
- lon (number) - долгота текущего местоположения (необязательный)
- radius (integer) - радиус поиска в км, по умолчанию 10 (необязательный)

## Часть 2: Пример ответа REST API (JSON)

{
  "status": "success",
  "code": 200,
  "data": {
    "shops": [
      {
        "id": "shop_001",
        "name": "Магазин у дома №5",
        "address": "г. Москва, ул. Ленина, 15",
        "distance_km": 1.2,
        "rating": 4.7,
        "image_url": "https://cdn.petrushka.ru/shops/001/logo.png",
        "external_url": "https://partner-shop-5.ru/petrushka",
        "work_hours": "09:00 - 21:00",
        "phone": "+7 (495) 123-45-67"
      },
      {
        "id": "shop_002",
        "name": "Супермаркет Ромашка",
        "address": "г. Москва, пр. Мира, 88",
        "distance_km": 2.5,
        "rating": 4.2,
        "image_url": "https://cdn.petrushka.ru/shops/002/logo.png",
        "external_url": "https://romashka.ru/promo/petrushka",
        "work_hours": "08:00 - 23:00",
        "phone": "+7 (495) 987-65-43"
      },
      {
        "id": "shop_003",
        "name": "Продуктовый рай",
        "address": "г. Москва, ул. Пушкина, 10",
        "distance_km": 3.1,
        "rating": 4.5,
        "image_url": "https://cdn.petrushka.ru/shops/003/logo.png",
        "external_url": "https://product-rai.ru/partner",
        "work_hours": "09:00 - 22:00",
        "phone": "+7 (495) 555-55-55"
      }
    ],
    "total": 3
  }
}

## Описание полей ответа

- status (string) - статус ответа (success / error)
- code (integer) - HTTP код ответа
- data.shops[].id (string) - уникальный идентификатор магазина
- data.shops[].name (string) - название магазина
- data.shops[].address (string) - физический адрес
- data.shops[].distance_km (float) - расстояние от пользователя в км
- data.shops[].rating (float) - рейтинг магазина (от 0 до 5)
- data.shops[].image_url (string) - ссылка на логотип или фото магазина
- data.shops[].external_url (string) - ссылка на внешний ресурс партнера
- data.shops[].work_hours (string) - часы работы
- data.shops[].phone (string) - телефон магазина

## Важное примечание

При клике на плашку магазина в мобильном приложении должен открываться external_url во внешнем браузере или WebView. Это позволяет партнерам использовать свои собственные сайты или промо-страницы.

## Пример ответа при ошибке

{
  "status": "error",
  "code": 401,
  "error": {
    "code": "UNAUTHORIZED",
    "message": "Недействительный токен авторизации"
  }
}
