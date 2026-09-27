# Проверка доменов Adobe

Проверено 27 сентября 2026 года. Основной файл: [`domains/adobe.lst`](../domains/adobe.lst). Записи являются доменами и точными именами узлов, без схемы, пути и масок. При использовании списка важно проверить, считает ли загрузчик запись `adobe.com` правилом для всех поддоменов.

## Основа списка

| Область | Основание |
| --- | --- |
| Creative Cloud, приложения, вход, лицензирование, обновления, Fonts, Stock, Behance, Express, Firefly | [Сетевые требования Adobe](https://helpx.adobe.com/business/enterprise/manage-services/configure-services/network-endpoints.html): опубликованный минимальный перечень Adobe и подробные адреса по приложениям. При повторной проверке добавлены `creativecloud.com`, `adbecrsl.com`, `platform-cs-va6-adobe.io` и точные адреса хранилищ S3 из таблиц Adobe; `*.astockcdn.net` отражён корневым доменом. |
| Acrobat и Document Cloud | [Список адресов Acrobat](https://www.adobe.com/devnet-docs/acrobatetk/tools/AdminGuide/endpoints.html) отдельно указывает `acrobat.com`, `acrocomcontent.com`, `adobecontent.io`, а также вход, файлы, подписи и PDF Spaces на адресах Adobe. |
| Acrobat Sign | [Системные требования](https://helpx.adobe.com/sign/web/system-level-resources/system-requirements.html) и [переход с EchoSign на Adobe Sign](https://helpx.adobe.com/sign/web/settings-configuration/echosign-domain-change.html) подтверждают старые и новые зоны подписания и CDN. Обе пары сохранены, пока поддерживаются действующие учётные записи. |
| Frame.io | [Перечень Adobe для Frame.io](https://helpx.adobe.com/business/enterprise/manage-services/configure-services/network-endpoints.html) указывает `frame.io`, `f.io` и четыре точных адреса загрузки медиа в Amazon S3. |
| Lightroom, Photoshop и Firefly | [Перечень Adobe](https://helpx.adobe.com/business/enterprise/manage-services/configure-services/network-endpoints.html) содержит `directstorage.adbephotos.com`, `mds-cdn.infra.adobesensei.io` и два конкретных адреса Firefly в S3. |
| Портфолио | `myportfolio.com` и `prosite.com` перечислены в [документе Adobe](https://helpx.adobe.com/business/enterprise/manage-services/configure-services/network-endpoints.html). |
| Adobe Experience Manager, Dynamic Media, Marketo Engage, Commerce | [AEM Cloud](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/custom-domain-names/introduction), [Dynamic Media](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21940), [Marketo API](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/base-url) и [Commerce](https://experienceleague.adobe.com/en/docs/commerce-operations/installation-guide/prerequisites/authentication-keys) подтверждают основные продуктовые зоны. |
| Adobe Connect | [Сетевые требования Connect](https://helpx.adobe.com/adobe-connect/firewall-proxy-server-configuration-adobe-connect.html) указывают `*.adobeconnect.com`; для аудио и видео дополнительно нужны WebRTC и соответствующие порты. |
| Короткие ссылки и веб-инструменты PDF | Adobe описывает [адреса `.new`](https://blog.adobe.com/en/publish/2021/02/02/adobe-adds-new-acrobat-tools-to-tackle-pdf-tasks-in-the-browser); ссылки `adobe.ly` использует [официальная документация Firefly](https://developer.adobe.com/firefly-services/docs/guides/). `adobestock.com` подтверждён [сотрудником Adobe в сообществе](https://community.adobe.com/questions-38/adobe-stock-submission-hacked-329253) как адрес переадресации. |

## Сверка с сообществом

Список [v2fly / adobe](https://github.com/v2fly/domain-list-community/blob/master/data/adobe) использован для поиска пропущенных продуктовых зон. В нём есть исторические адреса, рекламные узлы и отдельный [замороженный список активации](https://github.com/v2fly/domain-list-community/blob/master/data/adobe-activation). Они не перенесены без подтверждения актуальными документами Adobe. В частности, длинный список адресов активации не нужен рядом с правилом для `adobe.com`.

## Отбор внешних адресов

В основной список вошли точные S3-адреса установочных пакетов, Firefly, Frame.io, Lightroom, Stock и других приложений, а также четыре адреса ArkoseLabs для проверки входа, которые [Adobe прямо перечисляет](https://helpx.adobe.com/business/enterprise/manage-services/configure-services/network-endpoints.html). Широкие зоны `amazonaws.com`, `cloudfront.net`, `googleapis.com`, `githubusercontent.com`, `bing.com` и общие адреса платёжных, аналитических и коммуникационных систем целиком не добавлены: на них работают многие другие сервисы. Это может оставить отдельные функции или интеграции без нужного адреса. Адреса рекламных и аналитических систем Adobe Experience Cloud также не добавлены: они встречаются на сторонних сайтах и не относятся к доступу пользователя к приложениям Adobe.

Клиентские сайты Adobe Experience Manager и Adobe Commerce часто работают на собственных доменах организаций. Такие домены нельзя надёжно перечислить общим списком Adobe. Адреса сторонних поставщиков, включая средства входа организации и интеграции Frame.io, зависят от конкретной настройки.

## Пределы проверки

Adobe [предупреждает](https://helpx.adobe.com/business/enterprise/manage-services/configure-services/network-endpoints.html), что даже её перечень может меняться и не включает каждый адрес. Отдельные функции используют WebSocket и порты, которые список доменов сам по себе не настраивает. Доступность продукта также зависит от страны, учётной записи, подписки и настроек сети. Проверка основана на опубликованных источниках, без сетевых журналов всех приложений Adobe.
