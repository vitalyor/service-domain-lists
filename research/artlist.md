# Artlist: проверка доменов

Проверено 27 сентября 2026 года. [Единый список](../domains/artlist.lst) относится к платформе `artlist.io`: музыкальному каталогу, SFX, стоковому видео, шаблонам, AI Toolkit, Studio, Flows, Enterprise API, справке и Artlist Hub. Запись `artlist.io` должна распространяться на поддомены; это зависит от программы, загружающей список.

## Почему включены эти адреса

| Адрес | Наблюдение |
| --- | --- |
| `artlist.io` | [Официальный сайт](https://artlist.io/) с каталогом, аккаунтом и продуктами. На его публичных страницах найдены `toolkit.artlist.io`, `studio.artlist.io`, `flows.artlist.io`, `search-api.artlist.io`, `cms-public-artifacts.artlist.io`, `static-videos.artlist.io`, `help.artlist.io`, `developer.artlist.io` и другие поддомены. Все они покрыты одной корневой записью при указанном выше поведении загрузчика. [Enterprise API](https://developer.artlist.io/welcome) тоже размещён в этой зоне. |
| `artlist-dev.imgix.net` | Изображения и элементы интерфейса непосредственно загружались на публичных страницах [Artlist](https://artlist.io/), [Studio](https://artlist.io/studio) и [каталога музыки](https://artlist.io/royalty-free-music). Несмотря на слово `dev` в имени, этот адрес используется публичным сайтом. |
| `artlist-albums.imgix.net` | Обложки альбомов на [странице музыки](https://artlist.io/royalty-free-music). |
| `artlist-images.imgix.net` | Иллюстрации [каталога SFX](https://artlist.io/sfx). |
| `artlist-content-images.imgix.net` | Изображения на [страницах видео](https://artlist.io/stock-footage) и [шаблонов](https://artlist.io/video-templates). |
| `artlist-templates.imgix.net` | Превью [видеошаблонов](https://artlist.io/video-templates). |
| `artgrid.imgix.net` | Обложки видео на [странице Artlist Stock Footage](https://artlist.io/stock-footage). [Независимый разбор публичных метаданных](https://parse.bot/marketplace/eecf9ccd-8d65-4788-8520-0e7764a0f87a/artlist-io-api) также приводит это точное имя для миниатюр; оно нужно каталогу Artlist, хотя содержит старую марку Artgrid. |
| `artlist-toolkit-generations.imgix.net` | Изображения на публичной странице [AI Toolkit](https://toolkit.artlist.io/). |
| `challenges.cloudflare.com` | На публичных страницах [Artlist](https://artlist.io/) и [AI Toolkit](https://toolkit.artlist.io/) загружается скрипт Cloudflare Turnstile; адрес может участвовать в проверке входа. Это общая служба для множества сайтов. |
| `js.chargebee.com` | Скрипт Chargebee обнаружен на странице [AI Toolkit](https://toolkit.artlist.io/voice-over); [Artlist описывает](https://help.artlist.io/hc/en-us/articles/29508665950109-Managing-Artlist-s-payments-billing-cycles-payment-methods-and-subscription-changes) управление подпиской и платежами. Адрес нужен для сценариев оплаты, а не для просмотра каталога, и используется другими сервисами. |

Публичные страницы проверены в браузере без входа в аккаунт. Сверены главная страница, музыка, SFX, видео, шаблоны, AI Toolkit, Studio, Flows и Tools. В качестве дополнительных свидетельств использованы [справка по загрузке материалов](https://help.artlist.io/hc/en-us/articles/29596510418461-Downloading-Artlist-s-assets), [справка по Artlist Hub](https://help.artlist.io/hc/en-us/articles/29671103091613-Using-the-Artlist-Hub), [расширение для Premiere Pro](https://help.artlist.io/hc/en-us/articles/29671537279901-Using-the-Artlist-Library-extension) и [публичные метаданные видео](https://parse.bot/marketplace/eecf9ccd-8d65-4788-8520-0e7764a0f87a/artlist-io-api). Готового официального перечня сетевых адресов для всех функций Artlist не найдено.

## Границы списка

Artlist владеет [Motion Array](https://help.artlist.io/hc/en-us/articles/29508665950109-Managing-Artlist-s-payments-billing-cycles-payment-methods-and-subscription-changes), а [Artgrid](https://artlist.io/blog/artlist-impel-partnership/) — отдельная площадка компании. Их собственные сайты `motionarray.com` и `artgrid.io` не включены: это отдельные продукты со своими аккаунтами и загрузками. При этом точный CDN `artgrid.imgix.net` включён, потому что он используется в каталоге самого Artlist. [FXhome закрыт в 2025 году](https://artlist.zendesk.com/hc/en-us/articles/25112168034845-FXhome-sunset) и не включён.

На страницах также обнаружены аналитика, реклама, соцсети, cookie-сервисы и шрифты. Их присутствие не доказывает необходимость для каталога, загрузки и генерации; широкие зоны этих платформ не включены. Вход через Google или Facebook, а также корпоративный SSO могут требовать адресов выбранного провайдера входа. Поскольку это общие для многих сайтов адреса, в список они не входят. При покупке может появиться дополнительный платёжный узел, который не удалось проверить без оформления заказа.

Проверка без подписки не даёт увидеть конечные адреса всех скачиваний, обновлений Artlist Hub и результатов AI-генерации. Подписанные URL и CDN могут меняться. Поэтому список не следует считать гарантированно полным для каждого тарифа и сценария; новые адреса нужно подтверждать конкретным запросом и добавлять точечно.
