# Telegram: проверка доменов и границ списка

Проверено 27 сентября 2026 года. В основном файле [`telegram.lst`](../domains/telegram.lst) собраны домены Telegram и связанных с ним сайтов. Запись предполагает охват поддоменов: например, `telegram.org` должна покрывать `web.telegram.org`, `api.telegram.org`, `my.telegram.org` и адреса обновления приложения. Это поведение зависит от программы, загружающей список.

## Основной файл

[Официальный перечень Telegram](https://core.telegram.org/bug-bounty) прямо называет `telegram.org`, `t.me`, `tg.dev`, `telegram.me`, `telesco.pe`, `stel.com`, `contest.com`, `quiz.directory` и `telegra.ph`. `stel.com` был пропущен в первой версии нашего списка: [код Telegram Desktop](https://github.com/telegramdesktop/tdesktop/blob/dev/Telegram/SourceFiles/mtproto/mtproto_config.cpp) использует `apv3.stel.com` для резервной конфигурации.

Дополнительные фирменные зоны и имена для публикаций, файлов и ссылок сверены с [документацией глубоких ссылок](https://core.telegram.org/api/links), [конфигурацией клиента](https://core.telegram.org/api/config) и [подборкой сообщества](https://github.com/v2fly/domain-list-community/blob/master/data/telegram). Список сообщества помог найти кандидатов, но сам по себе не доказывает, что каждый домен принадлежит Telegram.

В списке itdog есть ещё `telega.one` и `ton.org`. Первый предоставляет зеркало сайта Telegram, но не включён в официальный перечень доменов Telegram; второй относится к отдельной экосистеме TON. Открытие сторонних ботов и Mini Apps может потребовать адресов их разработчиков: [Telegram позволяет запускать Mini Apps с адреса самого приложения](https://core.telegram.org/bots/webapps), и конечного перечня таких доменов нет.

## Дополнительный файл: восстановление соединения

[`telegram-bootstrap.lst`](../domains/telegram-bootstrap.lst) содержит точные адреса сторонних платформ, которые отдельные официальные клиенты используют при поиске резервной конфигурации. Подключать его следует только если нужны эти сценарии: адреса Google, Cloudflare и Microsoft обслуживают также другие приложения.

| Адрес | Основание |
| --- | --- |
| `dns.google.com`, `mozilla.cloudflare-dns.com` | [Исходный код Telegram Desktop](https://github.com/telegramdesktop/tdesktop/blob/dev/Telegram/SourceFiles/mtproto/special_config_request.cpp) использует их для запросов DNS поверх HTTPS. |
| `dns.google` | [TDLib](https://github.com/tdlib/td/blob/master/td/telegram/ConfigManager.cpp) использует новый адрес Google DNS. |
| `firebaseremoteconfig.googleapis.com`, `firestore.googleapis.com` | В [Telegram Desktop](https://github.com/telegramdesktop/tdesktop/blob/dev/Telegram/SourceFiles/mtproto/special_config_request.cpp) предусмотрены резервные пути через Firebase и Firestore. |
| `reserve-5a846.firebaseio.com` | Точный проект резервной конфигурации в [TDLib](https://github.com/tdlib/td/blob/master/td/telegram/ConfigManager.cpp). |
| `software-download.microsoft.com`, `tcdnb.azureedge.net` | Резервный путь конфигурации в [TDLib](https://github.com/tdlib/td/blob/master/td/telegram/ConfigManager.cpp). `tcdnb.azureedge.net` указан там как HTTP Host; фактическое сетевое имя может быть `software-download.microsoft.com`. |

Этот файл не означает, что все перечисленные адреса используются при каждом запуске или на каждой платформе. Он добавляет варианты восстановления, обнаруженные в коде; назначение отдельных путей может измениться с обновлением клиента.

## Почему доменов всё равно недостаточно

Клиент подключается к дата-центрам по [адресам, полученным из конфигурации](https://core.telegram.org/api/datacenter). Популярные файлы могут идти через [отдельные CDN-центры](https://core.telegram.org/cdn), а звонки — через [прямые соединения или ретрансляторы](https://core.telegram.org/api/end-to-end/video-calls). Эти соединения могут обращаться сразу к IP-адресу, без DNS-запроса к домену из списка. Поэтому даже оба файла вместе покрывают веб-адреса и часть восстановления, но не гарантируют полный охват сообщений, медиа и звонков нативного приложения.
