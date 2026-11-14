# Списки доменов сервисов

Здесь собраны текстовые списки доменов, сгруппированные по сервисам. Для каждого сервиса достаточно одной ссылки: связанные с его работой адреса сторонних платформ включены в тот же файл. Каждый список доступен по прямой ссылке.

## Списки

| Сервис | Файл | Прямая ссылка |
| --- | --- | --- |
| OpenAI и ChatGPT | [`domains/openai.lst`](domains/openai.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/openai.lst) |
| Anthropic и Claude | [`domains/anthropic.lst`](domains/anthropic.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/anthropic.lst) |
| Google AI | [`domains/google-ai.lst`](domains/google-ai.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/google-ai.lst) |
| YouTube | [`domains/youtube.lst`](domains/youtube.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/youtube.lst) |
| Adobe | [`domains/adobe.lst`](domains/adobe.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/adobe.lst) |
| Boris FX | [`domains/borisfx.lst`](domains/borisfx.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/borisfx.lst) |
| Artlist | [`domains/artlist.lst`](domains/artlist.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/artlist.lst) |
| Cloudflare | [`domains/cloudflare.lst`](domains/cloudflare.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/cloudflare.lst) |
| CloudFront | [`domains/cloudfront.lst`](domains/cloudfront.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/cloudfront.lst) |
| DigitalOcean | [`domains/digitalocean.lst`](domains/digitalocean.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/digitalocean.lst) |
| Discord | [`domains/discord.lst`](domains/discord.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/discord.lst) |
| Google Meet | [`domains/google-meet.lst`](domains/google-meet.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/google-meet.lst) |
| Google Play | [`domains/google-play.lst`](domains/google-play.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/google-play.lst) |
| HDRezka | [`domains/hdrezka.lst`](domains/hdrezka.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/hdrezka.lst) |
| Hetzner | [`domains/hetzner.lst`](domains/hetzner.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/hetzner.lst) |
| Meta | [`domains/meta.lst`](domains/meta.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/meta.lst) |
| OVHcloud | [`domains/ovh.lst`](domains/ovh.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/ovh.lst) |
| Roblox | [`domains/roblox.lst`](domains/roblox.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/roblox.lst) |
| Telegram | [`domains/telegram.lst`](domains/telegram.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/telegram.lst) |
| TikTok | [`domains/tiktok.lst`](domains/tiktok.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/tiktok.lst) |
| X / Twitter | [`domains/twitter.lst`](domains/twitter.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/twitter.lst) |

Для новых списков есть [разбор источников и ограничений по каждому сервису](research/catalog-2026.md). Две уже существовавшие подборки, Google AI и YouTube, проверены повторно; они сохранены отдельными файлами.

Результаты повторной проверки всех файлов приведены в [журнале аудита](research/audit-2026-09-27.md).

Список Telegram также содержит адреса сторонних служб, через которые отдельные клиенты получают резервную конфигурацию. Их назначение и ограничения описаны в [исследовании Telegram](research/telegram.md).

## Формат

В файле один домен на строку, без `https://`, путей и масок. Например:

```text
openai.com
chatgpt.com
```

Прямую ссылку можно добавить в приложение, которое загружает текстовые списки доменов по URL. То, как приложение обрабатывает поддомены и порядок правил, зависит от его настроек.

## Список OpenAI

Список составлен по [сетевым рекомендациям OpenAI](https://help.openai.com/en/articles/9247338-network-recommendations-for-chatgpt-errors-on-web-and-apps), [подборке сообщества v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/openai) и наблюдениям за соединениями приложения. Это не официальный и не гарантированно полный перечень.

Некоторые домены принадлежат сторонним сервисам, например `auth0.com` и `intercom.io`, и могут использоваться другими приложениями. Нужность отдельных дополнительных CDN-доменов сейчас не подтверждена. Для некоторых функций, включая голосовой режим ChatGPT, одних доменных правил может быть недостаточно: [OpenAI описывает](https://help.openai.com/en/articles/9247338-network-recommendations-for-chatgpt-errors-on-web-and-apps) также соединения с изменяемыми IP-адресами.

## Список Anthropic и Claude

Основные домены взяты из [требований Anthropic к сети для Claude Desktop](https://code.claude.com/docs/en/desktop#network-access-requirements) и [Claude Code](https://code.claude.com/docs/en/network-config#network-access-requirements). Дополнительно включены `clau.de`, `claudemcpclient.com` и отдельный CDN-адрес из [списка сообщества v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/anthropic). При перепроверке также добавлены `claude.site` для опубликованных артефактов и `claude.new`, который перенаправляет на новый чат. Список охватывает домены сайта, приложений, API, документации, пользовательских материалов и MCP, но не может гарантировать работу каждой интеграции.

Для проверки при входе добавлен `challenges.cloudflare.com`: его использование на `claude.ai` подтверждено [отчётом пользователя Claude Desktop](https://github.com/anthropics/claude-code/issues/89264). Также включены домены сервиса защиты от мошенничества Sift: [Wappalyzer обнаруживает его на claude.ai](https://www.wappalyzer.com/technologies/analytics/sift/), а [документация Sift](https://developers.sift.com/docs/v204/curl/decisions-api/decision-webhooks) использует адреса в зонах `sift.com` и `siftscience.com`. Это сторонние сервисы, которые могут встречаться и на других сайтах.

Из списка v2fly добавлены остальные домены Anthropic: `claude.dev`, `ant.dev`, `anthropic.team`, `antspace.dev`, `claudepages.dev`. Домены `chatbotclaude.com`, `claudeacademy.com` и `claudestudio.com` зарегистрированы через MarkMonitor и стоят на DNS Cloudflare, то есть выглядят защитными; трафика на них почти нет.

Телеметрия Claude Code указана точными хостами, а не зонами целиком: `http-intake.logs.us5.datadoghq.com` и `browser-intake-us5-datadoghq.com` из [документации Anthropic](https://code.claude.com/docs/en/network-config#network-access-requirements), плюс `o1158394.ingest.us.sentry.io` из списка v2fly. Зоны `datadoghq.com` и `sentry.io` не включены: на них сидят тысячи чужих сервисов.

Stripe и Intercom (оплата и чат поддержки) не включены: в документации Anthropic их нет, а сами зоны слишком широкие. Если оплата или поддержка на `claude.ai` с этой машины не работает, добавьте `js.stripe.com`, `m.stripe.network` и `widget.intercom.io`, предварительно проверив их в сетевом журнале браузера.

Некоторые действия Claude Code обращаются к общим сторонним площадкам, например GitHub, npm и Google Cloud Storage. Эти домены не включены: они обслуживают множество других продуктов и не являются специфичными для Anthropic.

В этот же файл включены хосты JavaScript-библиотек, которые [Anthropic перечисляет для артефактов](https://code.claude.com/docs/en/desktop#network-access-requirements): `cdnjs.cloudflare.com`, `cdn.jsdelivr.net`, `cdn.tailwindcss.com`, `code.jquery.com`, `unpkg.com`. Без них части артефактов не работают, и запасного варианта у них нет, но эти хосты обслуживают и другие сайты. Шрифты Google (`fonts.googleapis.com`, `fonts.gstatic.com`) убраны: Anthropic называет их необязательными, без них артефакты рисуются запасными шрифтами, а сами хосты используют полинтернета.

## Список Google AI

Охватывает отдельные продукты Gemini, Gemini API, AI Studio, Gemini Notebook (ранее NotebookLM), Flow, Labs, Jules, Opal, Stitch, Antigravity, Gemini Code Assist и некоторые функции Gemini в Google Cloud и на мобильных устройствах. Список составлен по [требованиям Gemini Code Assist](https://docs.cloud.google.com/gemini/docs/codeassist/set-up-gemini), [списку сообщества v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind) и отчётам о работе отдельных продуктов. Подробности и границы проверки приведены в [исследовании](research/google-ai.md).

В список не входят YouTube, реклама, аналитика, карты, магазин приложений и общие статические ресурсы Google. Несколько общих адресов сохранены для входа и подтверждённых API: например, `accounts.google.com` и `oauth2.googleapis.com`. Для работы отдельных функций могут понадобиться дополнительные общие адреса из [официального списка сетевых зависимостей Gemini](https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings). Этот файл не охватывает целиком Google Workspace и не гарантирует доступность сервиса для конкретного аккаунта или региона.

## Список YouTube

Отдельный список основных адресов сайта, видео, изображений и API YouTube. Основан на [подборках v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/youtube) и [itdog](https://github.com/itdoginfo/allow-domains/blob/main/Services/youtube.lst). Домены `ggpht.com` и `jnn-pa.googleapis.com` могут использоваться и другими продуктами Google. Региональные варианты домена YouTube и сторонние дополнения не включены.

## Список Adobe

Охватывает основные продуктовые зоны Creative Cloud, Acrobat, Acrobat Sign, Firefly, Express, Fonts, Stock, Behance, Frame.io, Substance 3D, Adobe Connect, а также отдельные зоны Adobe Experience Manager, Dynamic Media, Marketo Engage и Commerce. Внешние адреса для загрузок и проверки входа добавлены только там, где они конкретно указаны Adobe. Основа — [сетевые требования Adobe](https://helpx.adobe.com/business/enterprise/manage-services/configure-services/network-endpoints.html), [перечень Acrobat](https://www.adobe.com/devnet-docs/acrobatetk/tools/AdminGuide/endpoints.html) и [требования Acrobat Sign](https://helpx.adobe.com/sign/web/system-level-resources/system-requirements.html). Разбор включений и ограничений — в [исследовании](research/adobe.md).

## Список Boris FX

Включает адреса Boris FX Hub для входа, лицензий и загрузок, а также подтверждённые сайты прежних продуктов и iZotope, вошедшего в Boris FX в 2026 году. Для iZotope добавлены точные узлы Native Access; они принадлежат отдельной компании и используются не только iZotope. Основной источник — [требования Boris FX Hub](https://support.borisfx.com/hc/en-us/articles/20359074635277-How-can-I-use-the-Hub-behind-a-firewall). Подробнее о старых версиях VEGAS и iZotope — в [исследовании](research/borisfx.md).

## Список Artlist

Один файл для сайта Artlist, каталогов музыки, SFX, видео и шаблонов, AI Toolkit, Studio, Flows и Artlist Hub. В него включены точные адреса CDN, найденные на публичных страницах, и адреса проверки входа и оплаты. [Исследование](research/artlist.md) объясняет каждый домен, границы проверки без подписки и почему отдельные сайты Motion Array и Artgrid не входят.

## Как добавить список

Создайте файл `domains/имя-сервиса.lst` с одним доменом на строку и добавьте ссылку на него в таблицу. Предложения по исправлению и дополнению списков можно оставлять в issues или pull requests.
