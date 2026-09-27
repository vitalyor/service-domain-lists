# Проверка новых списков сервисов

Дата проверки: 27 сентября 2026 года. В текстовых файлах указаны домены без схем, путей и масок. Предполагается, что программа, загружающая файл, применяет запись к домену и его поддоменам; это поведение следует проверить в самой программе. Адреса третьих сторон включены лишь там, где они прямо связаны с работой соответствующего сервиса. Списки не основаны на копировании одного готового набора: опубликованные наборы использованы для поиска кандидатов, а назначение и границы сверялись отдельно.

## Инфраструктурные платформы

### Cloudflare

Основные зоны сайта, DNS, Access, Tunnel, Workers, Pages, R2, CDNJS, Challenges и наблюдения за соединениями. [Workers](https://developers.cloudflare.com/workers/configuration/routing/workers-dev/), [Pages](https://developers.cloudflare.com/pages/how-to/redirect-to-custom-domain/), [R2](https://developers.cloudflare.com/r2/platform/limits/), [Access](https://developers.cloudflare.com/cloudflare-one/faq/getting-started-faq/), [Tunnel](https://developers.cloudflare.com/tunnel/concepts/routing/) и [Turnstile](https://developers.cloudflare.com/turnstile/spin/) подтверждают отдельные зоны. Для Images и Stream добавлены общие зоны выдачи [изображений](https://developers.cloudflare.com/images/optimization/hosted-images/serve-uploaded-images/) и [видео](https://developers.cloudflare.com/stream/faq/). Адреса проверки подключения клиента взяты из [сетевых требований Cloudflare One](https://developers.cloudflare.com/cloudflare-one/team-and-resources/devices/cloudflare-one-client/deployment/firewall/), а зоны браузерной изоляции — из [глобальных правил Cloudflare](https://developers.cloudflare.com/cloudflare-one/traffic-policies/global-policies/). [Список сообщества](https://github.com/v2fly/domain-list-community/blob/master/data/cloudflare) помог обнаружить вспомогательные имена. Часть доменов (`workers.dev`, `pages.dev`, `r2.dev`, `imagedelivery.net`, `videodelivery.net`, `cloudflarestream.com`, `challenges.cloudflare.com`, `cdnjs.com`) обслуживает чужие проекты и сайты; включение всей зоны затрагивает их тоже. Подключения к DNS по адресу `1.1.1.1` и к клиенту по фиксированным IP не задаются доменным списком.

### CloudFront

В файле только `cloudfront.net`. [AWS документирует](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/LinkFormat.html) выдачу доменов вида `d...cloudfront.net`, а также [собственные имена клиентов](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/CNAMEs.html). Поэтому `cloudfront.net` охватывает чужие сайты на стандартных адресах CDN, но не охватывает сайты с собственным доменом. Универсального конечного списка таких сайтов не существует. Адреса панели AWS не включены: это другой набор сервисов.

### DigitalOcean

[Панель и API](https://docs.digitalocean.com/reference/api/reference/domains/), [Spaces](https://docs.digitalocean.com/reference/api/spaces/), [CDN Spaces](https://docs.digitalocean.com/products/spaces/how-to/enable-cdn/) и [App Platform](https://docs.digitalocean.com/products/app-platform/how-to/manage-domains/) подтверждают основные зоны. [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/digitalocean) показывает дополнительные старые адреса; `do.co` сохранён как короткая ссылка, а неподтверждённые общие ресурсы не добавлены. `digitaloceanspaces.com` и `ondigitalocean.app`/`ondigitalocean.com` содержат проекты клиентов. Их собственные домены не перечисляются автоматически.

### Hetzner

Список включает сайт и облачную консоль, [Cloud API](https://docs.hetzner.com/cloud/api/getting-started/using-api/), [Storage Box](https://docs.hetzner.com/storage/storage-box/general/), [Storage Share](https://docs.hetzner.com/storage/storage-share/general/) и [Object Storage](https://docs.hetzner.com/storage/object-storage/overview/). Дополнительные фирменные и DNS-зоны сверены с [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/hetzner). Зоны хранения и серверов могут содержать ресурсы клиентов; пользовательские домены на инфраструктуре Hetzner не входят.

### OVHcloud

`ovhcloud.com` и `ovh.com` охватывают сайт и панель. [Документация API](https://api.eu.ovhcloud.com/what-is-ovh-api.html) подтверждает `eu.api.ovh.com`, [документация Object Storage](https://docs.ovhcloud.com/de/guides/storage-and-backup/object-storage/s3-location) — адреса вида `s3.<region>.io.cloud.ovh.net`. Для старых площадок сохранены `soyoustart.com` и `kimsufi.com`. `ovh.net` охватывает также часть клиентского хостинга и почты; это намеренно широкая зона, поэтому для узкой задачи лучше использовать конкретные адреса своего продукта.

## Общение и социальные сервисы

### Discord

`discord.com` покрывает веб-приложение и API; старый `discordapp.com` остаётся совместимым адресом после [переезда домена](https://support.discord.com/hc/en-us/articles/360042987951-Discordapp-com-is-now-Discord-com). [Статус](https://support.discord.com/hc/en-us/articles/115001310031-Voice-Connection-Errors), CDN, голосовые имена, ссылки приглашений и Activities сверены с [сообществом v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/discord) и [пользовательскими наблюдениями](https://github.com/Delitefully/DiscordLists/blob/master/domains.md). Узел загрузки вложений в Google Cloud Storage включён точечно. Голос может использовать UDP и динамические серверы; домены сами по себе не гарантируют передачу звука.

### Meta

Включены основные зоны Facebook, Instagram, Messenger, WhatsApp, Threads, Quest и Meta AI. Meta [перевела Threads с `threads.net` на `threads.com`](https://about.fb.com/news/2025/04/new-features-threads-web-experience/), но старый адрес оставлен для ссылок. [WhatsApp подтверждает `wa.me`](https://faq.whatsapp.com/5913398998672934); [страницы Meta](https://www.meta.com/brand/resources/meta/company-brand/) подтверждают состав продуктов. `metaaiusercontent.com` добавлен для пользовательских материалов Meta AI: домен [внесён представителем Meta в Public Suffix List](https://chromium.googlesource.com/chromium/src/+/master/net/base/registry_controlled_domains/effective_tld_names.dat). CDN и вспомогательные зоны сверены с [подборкой сообщества](https://github.com/v2fly/domain-list-community/blob/master/data/meta). Защитные регистрации, рекламные домены и внутренние адреса Facebook исключены: они не требуются для обычного использования продуктов.

### Telegram

Зоны сайтов, ссылок, веб-клиента, файлов, публикаций и Fragment сверены с [документацией Telegram](https://core.telegram.org/api/links), [Bot API](https://core.telegram.org/bots/api) и [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/telegram). Важное ограничение: клиенты MTProto получают [IP-адреса дата-центров](https://core.telegram.org/api/datacenter), а CDN тоже может быть задан [IP-адресом](https://core.telegram.org/cdn). Поэтому доменный список не может обеспечить полный охват нативного клиента. TON как отдельная экосистема в файл не включена.

### TikTok

Включены основной сайт, API, региональные зоны медиа и Live. [Документация TikTok](https://developers.tiktok.com/docs/en/tiktok-api-v2-introduction) подтверждает `open.tiktokapis.com`, а [примеры медиа](https://developers.tiktok.com/docs/en/display-api-get-started) показывают `tiktokcdn.com` и `tiktokcdn-us.com`. Региональные и исторические варианты сверены с [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/tiktok) и [пользовательской выборкой](https://github.com/Salad360/tiktok-domains/blob/main/domains.txt). Общие домены ByteDance, Akamai и рекламных партнёров исключены; набор CDN может меняться по региону.

### X / Twitter

Оставлены основные адреса сайта, старые ссылки, медиа и трансляций. [X объясняет работу `t.co`](https://help.x.com/en/using-x/url-shortener), а [документация видео](https://help.x.com/en/using-x/x-videos) называет `twimg.com`. Исторические варианты сверены с [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/twitter). Старые рекламные и промосайты исключены, поскольку они не нужны для ленты, сообщений и медиа.

## Google

### Google Meet

[Официальные сетевые требования](https://support.google.com/a/answer/1279090?hl=en) перечисляют адреса интерфейса, API, статических файлов и трансляций. Они шире [списка сообщества](https://github.com/itdoginfo/allow-domains/blob/main/Services/google_meet.lst), поэтому в файле добавлены подтверждённые зависимости входа и интерфейса. Общие Google-адреса могут использоваться другими продуктами. Аудио и видео Meet используют отдельные диапазоны IP и порты, о чём Google предупреждает в том же документе: доменов недостаточно для гарантии звонка.

### Google Play

[Google перечисляет адреса Play и обновлений Android](https://support.google.com/work/android/answer/10513641?hl=en): сайт, загрузки через `gvt1.com` и `dl.google.com`, проверку сети и Play Protect. Точные API и медиа-адреса дополнены по [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/google-play) и [itdog](https://github.com/itdoginfo/allow-domains/blob/main/Services/google_play.lst). Общие `google.com`, `googleapis.com`, `gstatic.com` и `googleusercontent.com` целиком не добавлены; из-за этого отдельные сценарии входа, платежей или предприятию могут потребовать дополнительных адресов. Загрузка приложений также зависит от устройства и доступности магазина в регионе.

### Google AI и YouTube

Для Google AI уже есть [отдельное подробное исследование](google-ai.md). Оно было повторно сверено с [требованиями Google для Gemini](https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings) и текущей [подборкой сообщества](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind); подтверждённого повода расширять его общими зонами Google сейчас нет.

YouTube сохранён отдельным файлом для сайта, встроенного плеера, API и медиа (`googlevideo.com`, `ytimg.com`, `ggpht.com`). Состав сверялся с [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/youtube) и [itdog](https://github.com/itdoginfo/allow-domains/blob/main/Services/youtube.lst). Множество страновых имён YouTube и адреса других продуктов Google не добавлены. На видео могут влиять динамические CDN, приложения и устройство.

## Roblox и HDRezka

### Roblox

[Официальная инструкция для сетей](https://en.help.roblox.com/hc/en-us/articles/115005744663-Troubleshooting-Education-Networks) перечисляет `roblox.com`, `rbxcdn.com` и два узла ArkoseLabs. Зоны инфраструктуры и коротких ссылок сверены с [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/roblox). Roblox указывает, что игровые сеансы используют UDP-порты 49152–65535 с изменяемыми IP-адресами. Этот файл охватывает домены запуска и ресурсов, но не обещает полный игровой трафик.

### HDRezka

У сервиса нет доступного надёжного официального перечня адресов. Кандидаты сверены по [списку itdog](https://github.com/itdoginfo/allow-domains/blob/main/Services/hdrezka.lst), [разрешениям расширения для браузера](https://chrome-stats.com/d/bledompcjiepahghecekpeodipnpbhpl) и [независимым сообщениям о зеркалах](https://github.com/dm17ryk/hdrezka-ext). В файл вошли только часто повторяющиеся домены. Для видеопотока подтверждён `voidboost.cc` в [сообщениях пользователей](https://4pda.to/forum/index.php?showtopic=1083801&st=2320); ещё один адрес `voidboost.one` указан в [сообщении сообщества 2026 года](https://github.com/StressOzz/Zapret-Manager/issues/947), а `static.voidboost.com` — в [разрешениях расширения](https://addons.mozilla.org/pl/firefox/addon/hdrezka-ratings-downloader/). Сходные названия не доказывают принадлежность одному оператору; зеркала могут смениться или оказаться поддельными. Проверка конкретной страницы и видеоплеера на своём устройстве остаётся необходимой.

## Сверка с готовыми подборками

[Списки itdog](https://github.com/itdoginfo/allow-domains/tree/main/Services) использовались для поиска пропусков, а не как шаблон. Например, в YouTube не включён `returnyoutubedislikeapi.com`, потому что это стороннее дополнение; в Telegram не включён `ton.org`, так как TON — отдельная экосистема; в TikTok не включены общие зоны ByteDance; в X/Twitter отброшены старые рекламные и промосайты. У HDRezka, наоборот, добавлены адреса видеопотока из свежих сообщений сообщества, которых нет в списке зеркал. Такие решения сохраняют границы сервисов и уменьшают случайный захват посторонних сайтов.
