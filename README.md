# Списки доменов сервисов

Здесь собраны текстовые списки доменов, сгруппированные по сервисам. Каждый список находится в отдельном файле и доступен по прямой ссылке.

## Списки

| Сервис | Файл | Прямая ссылка |
| --- | --- | --- |
| OpenAI и ChatGPT | [`domains/openai.lst`](domains/openai.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/openai.lst) |
| Anthropic и Claude | [`domains/anthropic.lst`](domains/anthropic.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/anthropic.lst) |
| Google AI | [`domains/google-ai.lst`](domains/google-ai.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/google-ai.lst) |
| YouTube | [`domains/youtube.lst`](domains/youtube.lst) | [Текстовый список](https://raw.githubusercontent.com/vitalyor/service-domain-lists/main/domains/youtube.lst) |

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

Некоторые действия Claude Code обращаются к общим сторонним площадкам, например GitHub, npm и Google Cloud Storage. Эти домены не включены: они обслуживают множество других продуктов и не являются специфичными для Anthropic.

## Список Google AI

Охватывает отдельные продукты Gemini, Gemini API, AI Studio, Gemini Notebook (ранее NotebookLM), Flow, Labs, Jules, Opal, Stitch, Antigravity, Gemini Code Assist и некоторые функции Gemini в Google Cloud и на мобильных устройствах. Список составлен по [требованиям Gemini Code Assist](https://docs.cloud.google.com/gemini/docs/codeassist/set-up-gemini), [списку сообщества v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind) и отчётам о работе отдельных продуктов. Подробности и границы проверки приведены в [исследовании](research/google-ai.md).

В список не входят YouTube, реклама, аналитика, карты, магазин приложений и общие статические ресурсы Google. Несколько общих адресов сохранены для входа и подтверждённых API: например, `accounts.google.com` и `oauth2.googleapis.com`. Для работы отдельных функций могут понадобиться дополнительные общие адреса из [официального списка сетевых зависимостей Gemini](https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings). Этот файл не охватывает целиком Google Workspace и не гарантирует доступность сервиса для конкретного аккаунта или региона.

## Список YouTube

Отдельный список основных адресов сайта, видео, изображений и API YouTube. Основан на [подборках v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/youtube) и [itdog](https://github.com/itdoginfo/allow-domains/blob/main/Services/youtube.lst). Домены `ggpht.com` и `jnn-pa.googleapis.com` могут использоваться и другими продуктами Google. Региональные варианты домена YouTube и сторонние дополнения не включены.

## Как добавить список

Создайте файл `domains/имя-сервиса.lst` с одним доменом на строку и добавьте ссылку на него в таблицу. Предложения по исправлению и дополнению списков можно оставлять в issues или pull requests.
