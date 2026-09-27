# Проверка доменов Google AI

Проверено 27 сентября 2026 года. Файл [`domains/google-ai.lst`](../domains/google-ai.lst) содержит по одному домену на строку без масок. Это подборка наблюдаемых и документированных адресов, а не официальный исчерпывающий перечень Google.

## Продукты и источники

| Область | Основание |
| --- | --- |
| Gemini в браузере и мобильном приложении | [Официальные настройки сетевого доступа](https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings) содержат адреса интерфейса, общих API, медиа, карт, видео и аналитики. [Пользовательский отчёт](https://github.com/itdoginfo/allow-domains/issues/129) дополняет мобильные и голосовые адреса; [отчёт о голосовом вводе](https://support.google.com/gemini/thread/364444281) подтверждает `speechs3proto2-pa.googleapis.com`. |
| AI Studio и Gemini API | [Список v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind) содержит домены сайта и внутренние API. [Документация Gemini API](https://ai.google.dev/api/all-methods) подтверждает `generativelanguage.googleapis.com`, включая [Live API через WebSocket](https://ai.google.dev/api/live). |
| Gemini Notebook | [Официальный список Google Workspace](https://knowledge.workspace.google.com/admin/getting-started/set-up-a-google-workspace-host-name-allowlist) содержит новый `notebook.google.com`; старые адреса и API приведены в [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind). |
| Flow и Google Labs | [Страница Flow](https://labs.google/fx/tools/flow) использует `labs.google`. [Наблюдение сообщества за переносом](https://github.com/ffroliva/gflow-cli/issues/642) подтверждает `flow.google.com` и смену способа обращения к серверу; [проверка генерации](https://github.com/ffroliva/gflow-cli/blob/develop/docs/LIVE_VERIFICATION_v0.67.0.md) показывает выдачу видео с `flow-content.google`. Старый и новый адреса приложения оставлены на переходный период. |
| Jules, Stitch, Opal, Antigravity | [Google называет адреса Jules и Stitch](https://blog.google/innovation-and-ai/products/io-2025-tools-to-try-globally/) и [адрес Opal](https://blog.google/innovation-and-ai/models-and-research/google-labs/opal-expansion/); [страница Antigravity](https://developers.googleblog.com/build-with-google-antigravity-our-new-agentic-development-platform/) подтверждает его собственную зону. Дополнительные адреса взяты из [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind). В [отчёте об ошибке Antigravity CLI](https://github.com/google-antigravity/antigravity-cli/issues/181) зафиксированы обращения к `daily-cloudcode-pa.googleapis.com` и `antigravity-unleash.goog`; адрес sandbox подтверждён только [проектом сообщества](https://github.com/luckdevx/opencode-antigravity/blob/main/docs/ANTIGRAVITY_API_SPEC.md). |
| Gemini Code Assist и Cloud | [Google перечисляет API и адреса входа](https://docs.cloud.google.com/gemini/docs/codeassist/set-up-gemini); [Vertex AI](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/start/quickstart) использует `aiplatform.googleapis.com`, а [Gemini Cloud Assist](https://docs.cloud.google.com/cloud-assist/use-gemini-cloud-assist-mcp) — `geminicloudassist.googleapis.com`. |
| Подписка и лимиты | [Google One управляет тарифами Google AI и дополнительными кредитами](https://support.google.com/googleone/answer/16476811); поэтому включён `one.google.com`. |

## Что учтено при отборе

- Общие адреса из официального списка Gemini включены точными именами. Это позволяет охватить зависимости интерфейса без правила на всю зону `google.com` или `googleapis.com`. Некоторые из этих адресов одновременно обслуживают поиск, YouTube, карты, магазин приложений и другие продукты Google.
- Адреса рекламных и аналитических служб сохранены, поскольку Google прямо включает их в [настройки сетевого доступа Gemini](https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings). Это не означает, что каждый из них нужен для каждого действия в Gemini.
- Для загрузки материалов Notebook и Stitch добавлен точный `contribution.usercontent.google.com` по [наблюдениям клиентов Notebook](https://github.com/teng-lin/notebooklm-py/blob/main/docs/architecture.md) и [сообщению в сообществе Google](https://discuss.ai.google.dev/t/compromised-mcp-key-stitch-antigravity/122992/6).
- Старый `aitestkitchen.withgoogle.com` оставлен для [исторических адресов экспериментов](https://discuss.ai.google.dev/t/gemini-image-generation-via-api/954); актуальные инструменты находятся на `labs.google` и `flow.google.com`.
- В отличие от [списка itdog](https://github.com/itdoginfo/allow-domains/blob/main/Services/google_ai.lst), общий `clients6.google.com` не добавлен: вместо него включены конкретные узлы из [v2fly](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind) и [документации Google](https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings).
- Приложения Gmail, Docs, Drive, Chrome и Cloud Console имеют собственные обширные зависимости. Здесь приведены их известные точки связи с отдельными продуктами Google AI, а не полный перечень адресов этих приложений.

## Сверка с подборками сообщества

| Подборка | Состояние на дату проверки | Вывод |
| --- | --- | --- |
| [v2fly / google-deepmind](https://github.com/v2fly/domain-list-community/blob/master/data/google-deepmind) | 43 записи; все отражены в основном файле | Хорошая основа для отдельных продуктов и внутренних API; не охватывает полный [список общих адресов Gemini от Google](https://knowledge.workspace.google.com/admin/generative-ai/gemini-app/gemini-app-firewall-settings). |
| [itdog / google_ai.lst](https://github.com/itdoginfo/allow-domains/blob/main/Services/google_ai.lst) | 28 записей; все, кроме общего `clients6.google.com`, отражены точными адресами | Не включает часть новых адресов Notebook, Flow, Code Assist и загрузок медиа. |
| [blackmatrix7 / Gemini](https://github.com/blackmatrix7/ios_rule_script/blob/master/rule/Clash/Gemini/Gemini.list) | 13 правил, обновлены в июне 2025 года | Помогают подтвердить старые адреса Gemini, но не учитывают многие продукты и переезды 2026 года. |

[MetaCubeX](https://raw.githubusercontent.com/MetaCubeX/meta-rules-dat/meta/geo/geosite/google-deepmind.yaml) публикует производный набор geosite; его совпадение с v2fly не считается независимым подтверждением каждого адреса.

## Пределы проверки

Google указывает, что набор используемых узлов зависит от браузера и состояния сети, а адреса могут появляться позднее. Подборку нельзя считать гарантией работы каждой функции без проверки конкретного устройства и аккаунта. [Google также сообщает](https://support.google.com/gemini/answer/13594961), что Gemini может определять местоположение по IP-адресу, данным аккаунта и, при разрешении, геопозиции устройства; один лишь список доменов не управляет этими сигналами.

Проверка выполнена по опубликованной документации, исходным текстам списков и отчётам с конкретными адресами запросов. Сетевые журналы всех приложений на личных устройствах не собирались, поэтому для отдельных функций могут понадобиться дополнительные адреса.
