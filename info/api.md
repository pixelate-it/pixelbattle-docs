---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 📌 API Pixel Battle

API - [**https://api.pixelbattle.fun/**](https://api.pixelbattle.fun/)

## Что необходимо для работы с API?

Вся подробная информация о требованиях к запросу предоставлена в интересующем вас EndPoint'е

## Endpoints



{% swagger method="get" path="/" baseUrl="https://api.pixelbattle.fun" summary="API root" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "error": false, 
    "reason": "PixelAPI v3 works! Good time for chill :D"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/users/:id" baseUrl="https://api.pixelbattle.fun" summary="Get user" %}
{% swagger-description %}
Позволяет получить информацию о пользователе из базы данных
{% endswagger-description %}

{% swagger-parameter in="path" required="true" name="id" type="String" %}
Discord user ID
{% endswagger-parameter %}

{% swagger-response status="404: Not Found" description="Пользователь не найден в БД" %}
```json
{
    "error": true,
    "reason": "EntryMissing"
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Пользователь найден в БД (пример)" %}
```json
{
    "userID": "663378999103324180",
    "cooldown": 1701451495266,
    "tag": "Pixelate It! Team",
    "username": "mirdukkkkk",
    "banned": false,
    "isMod": true
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/game" baseUrl="https://api.pixelbattle.fun" summary="Get game state" %}
{% swagger-description %}
Позволяет получить информацию о текущем состоянии игры
{% endswagger-description %}

{% swagger-response status="200: OK" description="Пример информации" %}
```json
{
    "name": "December",
    "cooldown": 500,
    "ended": false,
    "canvas": {
        "height": 80,
        "width": 160
    },
    "online": 5
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/pixels.bmp" baseUrl="https://api.pixelbattle.fun" summary="Get canvas" %}
{% swagger-description %}
Позволяет получить холст в виде картинки формата .bmp
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
Bits per pixel: 24 (3 channels)\
Resolution: canvas.width x canvas.height (here 160x80)

Example:

<img src="../.gitbook/assets/pixels.bmp" alt="" data-size="original">
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/pixels/tag" baseUrl="https://api.pixelbattle.fun" summary="Get tags info" %}
{% swagger-description %}
Позволяет получить информацию о тегах на холсте
{% endswagger-description %}

{% swagger-response status="200: OK" description="Пример информации" %}
```json
{
    "pixels": {
        "all": 12800,
        "used": 11234,
        "unused": 1566
    },
    "tags": [
        ["Pixelate It! Team", 10000],
        ["ing sqd.", 1234]
    ]
}
```
{% endswagger-response %}
{% endswagger %}
