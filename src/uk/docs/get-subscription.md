---
title: Як купити підписку

contributors: [LoSk-p, PaTara43]
tools:
  - Robonomics 2.4.0
    https://github.com/airalab/robonomics
---

**Сплачувати комісії за транзакції в блокчейні - це неприємно. Уявіть пристрій Інтернету речей, який надсилає телеметрію кожні 5-10 хвилин. Це може виявитися досить дорогим протягом місяця. Однією з ключових функцій мережі Robonomics є підписка на веб-сервіс Robonomics (RWS). Платіть щомісяця і забудьте про вартість транзакцій! Для теоретичного підґрунтя дивіться [цю](https://blog.aira.life/rws-overview-part-2-heterogeneous-tokenomics-afc209cc855) статтю.**


{% roboWikiNote {title:"Парачейн", type: "warning"}%}   Зверніть увагу, що цей посібник демонструє, як купити підписку на парачейн Robonomics Kusama. Ви також можете виконати всі ті ж самі кроки на вашому [локальному вузлі](/docs/run-dev-node).
Ще одна річ перед початком. Це "важкий" спосіб купити підписку. Існує звичайний спосіб зробити це через [Robonomics DApp](https://dapp.robonomics.network/#/).
{% endroboWikiNote %}

## Зробіть ставку на аукціоні

Підписки в Robonomics продаються за моделлю аукціону. Щоб отримати одну, вам потрібно зробити ставку на аукціоні та виграти її (не хвилюйтеся, це швидко).

У розділі `Розробник/Стан ланцюжка` ви можете побачити доступні аукціони.
Виберіть `rws` та `auctionQueue` та натисніть кнопку `+`, ви побачите ID доступних аукціонів:

{% roboWikiPicture {src:"docs/rws/queue.png", alt:"queue"} %}{% endroboWikiPicture %}

Ви можете побачити інформацію про будь-яку підписку за допомогою `rws` `auction` та ID аукціону (ID аукціону на зображенні - 79):

{% roboWikiPicture {src:"docs/rws/auction.png", alt:"auction"} %}{% endroboWikiPicture %}

У інформації про аукціон ви побачите поле `winner`, на даний момент воно має значення `null`, тому ніхто не має цієї підписки і ви можете її отримати. Для цього перейдіть до `Розробник/Екстранс`, виберіть свій обліковий запис та `rws -> bid`. Також встановіть ID аукціону (79) та кількість одиниць для ставки (більше 1000000000 Wn):

{% roboWikiPicture {src:"docs/rws/bid.png", alt:"bid"} %}{% endroboWikiPicture %}

Надішліть транзакцію та перевірте інформацію про аукціон з ID 79 (у розділі `Стан ланцюжка` виберіть `rws -> auction` та ID 79):

{% roboWikiPicture {src:"docs/rws/auc_win.png", alt:"auc_win"} %}{% endroboWikiPicture %}

Тепер у полі `winner` ви побачите адресу вашого облікового запису, це означає, що цей обліковий запис має підписку 79. Аукціон починається з першої ставки і триває кілька блоків, тому якщо хтось зробить більше токенів, ніж ви, в наступних кількох блоках, цей хтось стане переможцем і отримає підписку.

Тепер ви можете додати пристрої. Пристрої - це облікові записи, які можуть використовувати цю підписку та надсилати екстранси без комісії.
Щоб перевірити це, створіть новий обліковий запис без токенів та додайте його до пристроїв.

Щоб додати пристрої, виберіть `rws -> setDevices` в розділі `Розробник/Екстранс`. Потім натисніть кнопку `Додати елемент` та виберіть недавно створений обліковий запис без токенів:

{% roboWikiPicture {src:"docs/rws/set_devices.png", alt:"set_devices"} %}{% endroboWikiPicture %}

Надішліть транзакцію. Тепер ви можете перевірити список пристроїв у розділі `Стан ланцюжка` за допомогою `rws -> devices`. Там ви побачите адресу вашого облікового запису без токенів. Виберіть обліковий запис, який купив підписку, та натисніть `+`:

{% roboWikiPicture {src:"docs/rws/devices.png", alt:"devices"} %}{% endroboWikiPicture %}

Тепер ви можете спробувати [надіслати запуск](/docs/subscription-launch) екстранс, використовуючи підписку.