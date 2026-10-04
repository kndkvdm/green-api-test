# GREEN-API — тестовая HTML-страница

Тестовое задание на должность «Специалист технической поддержки 2 линии».

Одна статическая страница (`index.html`, без зависимостей и сборки), которая вызывает методы GREEN-API:

| Кнопка | Запрос |
|---|---|
| getSettings | `GET {apiUrl}/waInstance{idInstance}/getSettings/{apiTokenInstance}` |
| getStateInstance | `GET {apiUrl}/waInstance{idInstance}/getStateInstance/{apiTokenInstance}` |
| sendMessage | `POST …/sendMessage/…` — `{ chatId: "<phone>@c.us", message }` |
| sendFileByUrl | `POST …/sendFileByUrl/…` — `{ chatId, urlFile, fileName }` (имя файла берётся из ссылки) |

Ответ метода выводится в поле «Ответ» (только для чтения); ошибки HTTP показываются со статусом.

## Как проверить
1. Создать инстанс в [личном кабинете GREEN-API](https://console.green-api.com) и привязать номер по QR-коду.
2. Открыть страницу, ввести `idInstance`, `ApiTokenInstance` (и `apiUrl`, если в кабинете указан не `https://api.green-api.com`).
3. Нажать **getSettings** / **getStateInstance**, затем ввести номер (только цифры с кодом страны, например `77771234567`) и нажать **sendMessage** / **sendFileByUrl**.

Локально: `python3 -m http.server` в папке проекта и открыть `http://localhost:8000`.
