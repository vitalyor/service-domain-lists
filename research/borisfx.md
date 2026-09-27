# Проверка доменов Boris FX

Проверено 27 сентября 2026 года. Основной файл: [`domains/borisfx.lst`](../domains/borisfx.lst). Записи указаны без схемы, пути и масок. Для `borisfx.com` и других зон нужно проверить, что загрузчик охватывает также поддомены.

## Продукты и источники

| Область | Основание |
| --- | --- |
| Boris FX Hub: вход, лицензии, каталог продуктов, установки | [Официальная таблица сетевых адресов Hub](https://support.borisfx.com/hc/en-us/articles/20359074635277-How-can-I-use-the-Hub-behind-a-firewall) указывает `bfxlive.borisfx.com`, `bfxlivefrontend.borisfx.com`, `backend.borisfx.com`, `borisfx.com`, `cdn.borisfx.com`, `borisfxdownloads.com`, `activation.genarts.com` и `borisfx-com-res.cloudinary.com`. Поддомены `borisfx.com` покрыты одной записью. |
| Сайт, учётная запись и загрузки | [Статья Boris FX об учётной записи](https://support.borisfx.com/hc/en-us/articles/44321631000333-I-purchased-from-a-retailer-How-do-I-get-my-license-set-up) подтверждает `account.borisfx.com` для лицензий и установщиков. |
| Sapphire и старые площадки GenArts | Сайты [genarts.net](https://genarts.net/) и [genarts.org](https://genarts.org/products/sapphire/) сейчас публикуют страницы Boris FX. Это вспомогательные веб-адреса; для активации подтверждён именно `activation.genarts.com`. |
| Обучение и эфиры | [Boris FX Live](https://www.borisfxlive.com/company/about-us/) остаётся отдельным сайтом компании. |
| CrumplePop | [Страница продукта](https://borisfx.com/products/crumplepop/) указывает, что старые покупки и учётные записи на `crumplepop.com` продолжают работать; новые обновления идут через Boris FX. |
| VEGAS, Sound Forge и ACID | Версии 2026 года [устанавливаются через Boris FX Hub](https://support.borisfx.com/hc/en-us/articles/46925662192653-How-do-I-install-the-Boris-FX-applications-that-come-with-Vegas-Pro-Plus-2026-and-Vegas-Pro-Ultimate-2026). Для старых установщиков Boris FX [отсылает к прежней площадке](https://support.borisfx.com/hc/en-us/articles/43404139354637-How-do-I-recover-my-serial-numbers-and-installer-files-if-needed-in-the-future) `vegascreativesoftware.com`. |
| iZotope | [Boris FX сообщил о покупке iZotope](https://blog.borisfx.com/press/boris-fx-acquires-izotope-the-award-winning-leader-in-intelligent-audio-technology) в июле 2026 года. [iZotope](https://support.izotope.com/hc/en-us/articles/6658199993361-How-to-authorize-your-iZotope-software) описывает установку и активацию через Product Portal либо Native Access, а подписки — через [Native Access](https://support.izotope.com/hc/en-us/articles/6658256068753-How-to-set-up-your-iZotope-subscription). [Документ Native Instruments](https://support.native-instruments.com/support/solutions/articles/69000879319-native-access-is-stuck-on-startup-searching-for-the-latest-update-) называет точные узлы обновления клиента. |

## Границы списка

Список сторонних зон ограничен точным Cloudinary-узлом для баннера Hub и несколькими узлами Native Access. Последние принадлежат Native Instruments и используются также вне iZotope. Общий `amazonaws.com` из требований Native Access не добавлен, поскольку он обслуживает множество других продуктов. Для конкретной версии iZotope могут понадобиться дополнительные адреса загрузки, которые не опубликованы как устойчивый полный набор. Для продуктов из комплектов Sequoia и Samplitude [отдельные поставщики](https://support.borisfx.com/hc/en-us/articles/38965048376589-Installation-and-Activation-Third-Party-Software) требуют собственные учётные записи и установщики; они не включены.

В [таблице Boris FX Hub](https://support.borisfx.com/hc/en-us/articles/20359074635277-How-can-I-use-the-Hub-behind-a-firewall) активация через `activation.genarts.com` указана по HTTP на порту 80, остальные перечисленные обращения — по HTTPS на 443. Адреса могут измениться. Работа функции зависит также от лицензии, региона и настроек приложения. Проверка выполнена по опубликованным документам и действующим сайтам, без сетевых журналов всех продуктов Boris FX и iZotope.
