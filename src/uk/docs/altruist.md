---
title: Налаштування Altruist
contributors: [tubleronchik]
---

**Цей посібник проведе вас через процес налаштування та активації датчика Altruist Outdoor. Ви підключите датчик до Wi-Fi, налаштуєте його розташування та активуєте підписку за допомогою XRT токенів. Додатково надано інструкції щодо інтеграції датчика з Home Assistant через HACS або ручну установку.**

{% roboWikiNote {type: "warning"}%} Усі пристрої від Robonomics можна придбати на офіційному [вебсайті](https://robonomics.network/devices/).{% endroboWikiNote %}

## Активуйте підписку Robonomics

{% roboWikiNote {type: "okay"} %}Щоб завершити цей крок, переконайтеся, що у вас є принаймні 2-3 XRT токени у вашому обліковому записі `Robonomics Polkadot`.{% endroboWikiNote %}

1) Перейдіть на [сторінку підписки](https://robonomics.app/#/rws-buy) Robonomics dApp. 
2) Натисніть на **Account** і підключіть свій гаманець. Ваш адреса облікового запису та баланс будуть відображені.
Якщо у вас немає облікового запису, дотримуйтесь [цього посібника](https://wiki.robonomics.network/docs/create-account-in-dapp/), щоб створити його.

{% roboWikiPicture {src:"docs/altruist/altruist_syb_buy.jpg", alt:"сторінка підписки"} %}{% endroboWikiPicture %}

3) Натисніть `BUY SUBSCRIPTION` і підпишіть транзакцію. **Дочекайтеся завершення процесу активації**. 
4) Після активації ви будете перенаправлені на **сторінку налаштування**, де ви зможете побачити назву вашої підписки та дату її закінчення.

{% roboWikiPicture {src:"docs/altruist/altruist_setup_page.jpg", alt:"сторінка налаштування підписки"} %}{% endroboWikiPicture %}

5) **Збережіть адресу вашого облікового запису** — вона знадобиться вам під час налаштування сенсора. Ви можете скопіювати її з розділу "ВЛАСНИК" або натиснувши на ім'я вашого облікового запису у верхньому правому куті та вибравши кнопку копіювання.

## Налаштування сенсора

{% roboWikiNote {type: "warning", title: "ІНФОРМАЦІЯ"}%} Сенсор може бути підключений лише до Wi-Fi мережі 2.4GHz.{% endroboWikiNote %}

1) **Підключіть сенсор** до розетки.
2) Плата створить Wi-Fi мережу з назвою Altruist-xxxxxxxxx. Підключіться до неї з вашого телефону або комп'ютера. Ви повинні автоматично отримати запит на відкриття вікна авторизації.
- Якщо ні, відкрийте браузер і перейдіть на 192.168.4.1.

{% roboWikiPicture {src:"docs/altruist/on_board.png", alt:"altruist-сенсор"} %}{% endroboWikiPicture %}

3) **Налаштуйте параметри Wi-Fi**:
- Виберіть вашу Wi-Fi мережу зі списку або введіть її вручну, якщо вона не з'являється.
- Введіть пароль у полі "НАЛАШТУВАННЯ WI-FI".

4) **Введіть ваші дані Robonomics**:
- Вставте адресу власника RWS, яку ви скопіювали раніше, у відповідне поле.

5) **Встановіть місцезнаходження сенсора**:
- Введіть координати місця встановлення сенсора.
- Ви можете знайти координати за допомогою онлайн-карт або перетворити адресу в широту/довготу за [цим посиланням.](https://www.latlong.net/convert-address-to-lat)-long.html)

{% roboWikiNote {type: "warning", title: "ПОПЕРЕДЖЕННЯ"}%}Координати сенсора будуть відображені на загальнодоступній карті. Якщо ви не хочете показувати свою приватну інформацію, вкажіть близькі, але не точні координати.{% endroboWikiNote %}

{% roboWikiPicture {src:"docs/altruist/sensor_setup.png", alt:"altruist-sensor-wifi"} %}{% endroboWikiPicture %}

6) **Скопіюйте "Адресу Робономіки" Altruist**:
- Ви знайдете її у верхній частині сторінки. Збережіть її для останнього кроку.

{% roboWikiPicture {src:"docs/altruist/address.jpg", alt:"altruist address"} %}{% endroboWikiPicture %}

7) Натисніть "**Зберегти конфігурацію та перезавантажити**" внизу сторінки. Плата перезавантажиться і підключиться до вказаної Wi-Fi мережі.

## Активація Altruist
Останній крок у процесі налаштування - додавання **адреси Altruist** до вашої **Підписки Робономіки**.

1) Поверніться на [Сторінку налаштування](https://robonomics.app/#/rws-setup).

2) Прокрутіть вниз до розділу "**Користувачі в підписці**".

3) У полі "**Додати користувача**" вставте **адресу Робономіки Altruist**, яку ви скопіювали раніше.

{% roboWikiPicture {src:"docs/altruist/add_user.jpg", alt:"add user"} %}{% endroboWikiPicture %}

4) Натисніть **кнопку плюс (+)** і підпишіть повідомлення.

5) Дочекайтеся завершення операції.

Ось і все! Ваше налаштуваннятепер завершено. 🎉

Тепер ви можете знайти свій Altruist на карті [Robonomics Sensors Social](https://sensors.social/#). 🚀

{% roboWikiPicture {src:"docs/altruist/map.jpg", alt:"sensor map"} %}{% endroboWikiPicture %}

## Home Assistant

Існує два способи додати **Altruist** до **Home Assistant**:

### Варіант 1: HACS (Рекомендовано)

Найпростіший спосіб додати **Altruist** - через **HACS**. Ви можете знайти короткий посібник з налаштування [тут](https://hacs.xyz/docs/use/)

**Кроки**:
1) Після встановлення HACS відкрийте його.

2) Натисніть **три крапки** у верхньому правому куті та виберіть "**Custom repositories**".

3) У спливаючому вікні введіть наступну URL-адресу:

```
https://github.com/airalab/altruist-homeassistant-integration
```
4) Встановіть тип на "**Integration**" і натисніть "**ADD**".

{% roboWikiPicture {src:"docs/altruist/hacs.jpg", alt:"altruist-add"} %}{% endroboWikiPicture %}

5) Знайдіть інтеграцію **Altruist Sensor**.

6) Натисніть кнопку **Download**, потім перезапустіть **Home Assistant** після встановлення інтеграції.

{% roboWikiPicture {src:"docs/altruist/integration.jpg", alt:"altruist-hacs"} %}{% endroboWikiPicture %}

### Варіант 2: Ручне встановлення

1) Під користувачем `homeassistant` клонувати репозиторій проекту:

{% codeHelper { copy: true}%}

```shell
  git clone https://github.com/airalab/altruist-homeassistant-integration.git
```

{% endcodeHelper %}

2) Якщо у вас вже є будь-які користувацькі інтеграції, перемістіть папку `altruist` до вашого каталогу `custom_components`:

{% codeHelper { copy: true}%}

```
cd altruist-homeassistant-integration
mv custom_components/altruist ~/.homeassistant/custom_components/
```

{% endcodeHelper %}

3) Якщо у вас **немає** жодних користувацьких інтеграцій, перемістіть весь каталог custom_components:

{% codeHelper { copy: true}%}

 ```
cd altruist-homeassistant-integration
mv custom_components/ ~/.homeassistant/
```

{% endcodeHelper %}

## Конфігурація

Після встановлення та перезапуску Home Assistant, інтеграція автоматично виявить Altruist у вашій мережі.

1) Перейдіть до **Налаштування → Пристрої та Сервіси**.

2) Додайте **Altruist Sensor**.

{% roboWikiPicture {src:"docs/altruist/add_altruist.jpg", alt:"discover altruist"} %}{% endroboWikiPicture %}

Це все! 🚀 Ваш Altruist Sensor тепер інтегровано з Home Assistant.