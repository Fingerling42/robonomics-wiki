---
title: Налаштування Altruist
contributors: [tubleronchik]
---

**Цей посібник проведе вас через процес налаштування та активації датчика Altruist Outdoor. Ви підключите датчик до Wi-Fi, налаштуєте його розташування та активуєте підписку за допомогою XRT токенів. Додатково надано інструкції щодо інтеграції датчика з Home Assistant через HACS або ручну установку.**

{% roboWikiNote {type: "warning"}%} Усі пристрої від Robonomics можна придбати на офіційному [вебсайті](https://robonomics.network/devices/).{% endroboWikiNote %}

## Активуйте підписку Robonomics

{% roboWikiNote {type: "okay"} %}Щоб завершити цей крок, переконайтеся, що у вас є принаймні 2-3 XRT токени на вашому `Robonomics Polkadot` рахунку.{% endroboWikiNote %}

1) Перейдіть на [сторінку підписки](https://robonomics.app/#/rws-buy) Robonomics dApp. 
2) Натисніть **Account** і підключіть свій гаманець. Ваш адреса рахунку та баланс будуть відображені.
Якщо у вас немає рахунку, дотримуйтесь [цього посібника](https://wiki.robonomics.network/docs/create-account-in-dapp/), щоб створити його.

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

{% roboWikiPicture {src:"docs/altruist/networks.png", alt:"altruist-сенсор", small: true} %}{% endroboWikiPicture %}

3) **Налаштуйте параметри Wi-Fi**:
- Виберіть вашу Wi-Fi мережу зі списку або введіть її вручну, якщо вона не з'являється.
- Введіть пароль у полі "НАЛАШТУВАННЯ WI-FI".
- Якщо у вас є кілька пристроїв Altruist у тій самій мережі, змініть Локальне Ім'я Хоста. Після налаштування WiFi ви зможете підключитися до вашого сенсора, використовуючи це ім'я хоста.

{% roboWikiPicture {src:"docs/altruist/wifi_creds.png", alt:"altruist-сенсор", small: true} %}{% endroboWikiPicture %}

4) **Зберегти конфігурацію**
- Натисніть кнопку `Зберегти конфігурацію та перезапустити` і зачекайте, поки сенсор підключиться до WiFi. Після підключення він відобразить свою нову IP-адресу — скопіюйте її, оскільки це альтернативний спосіб підключення до ваших сенсорів після налаштування.

{% roboWikiPicture {src:"docs/altruist/connected.png", alt:"altruist-sensor", small: true} %}{% endroboWikiPicture %}

5) **Введіть ваші дані Robonomics**:
- Відкрийте веб-інтерфейс Altruist за адресою http://altruist.local (або використовуйте ваше власне локальне ім'я хоста з додаванням `.local`, якщо ви його змінили). Потім перейдіть на сторінку `Конфігурація`.
- У розділі `Robonomics` вставте адресу власника RWS, яку ви скопіювали раніше, у відповідне поле.

6) **Встановіть місцезнаходження сенсора**:
- У розділі `GPS & Temperature Correction` введіть координати місця встановлення сенсора.
- Ви можете знайти координати за допомогою онлайн-карт або перетворити адресу на широту/довготу за [цим посиланням.](https://www.latlong.net/convert-address-to-lat-long.html)

{% roboWikiNote {type: "warning", title: "УВАГА"}%}Координати сенсора будуть відображені на загальнодоступній карті. Якщо ви не хочете показувати вашу приватну інформацію, вкажіть близькі, але не точні координати.{% endroboWikiNote %}

{% roboWikiPicture {src:"docs/altruist/robo-gps.png", alt:"altruist-sensor-wifi", small: true} %}{% endroboWikiPicture %}

7) **Скопіюйте "Адресу Robonomics" Altruist**:
- Ви знайдете це у верхній частині сторінки. Збережіть це для останнього кроку.

{% roboWikiPicture {src:"docs/altruist/address.jpg", alt:"altruist address",  small: true} %}{% endroboWikiPicture %}

8) Натисніть "**Зберегти конфігурацію та перезапустити**" внизу сторінки. Плата перезавантажиться.

## Активація Altruist
Останній крок у процесі налаштування - додавання **адреси Altruist** до вашої **підписки Robonomics**.

1) Поверніться на [сторінку налаштування](https://robonomics.app/#/rws-setup).

2) Прокрутіть вниз до розділу "**Користувачі в підписці**".

3) У полі "**Додати користувача**" вставте **адресу Altruist Robonomics**, яку ви скопіювали раніше.

{% roboWikiPicture {src:"docs/altruist/add_user.jpg", alt:"add user"} %}{% endroboWikiPicture %}

4) Натисніть **кнопку плюс (+)** та підпишіть повідомлення.

5) Дочекайтеся завершення операції.

Це все! Ваше налаштування завершено. 🎉

Тепер ви можете знайти свій Altruist на карті [Robonomics Sensors Social](https://sensors.social/#). 🚀

{% roboWikiPicture {src:"docs/altruist/map.jpg", alt:"sensor map"} %}{% endroboWikiPicture %}

## Home Assistant

Існує два способи додати **Altruist** до **Home Assistant**:

### Варіант 1: HACS (рекомендовано)

Найпростіший спосіб додати **Altruist** - через **HACS**.Ви можете знайти короткий посібник з налаштування [тут](https://hacs.xyz/docs/use/)

**Кроки**:
1) Після встановлення HACS, відкрийте його.

2) Натисніть на **три крапки** у верхньому правому куті та виберіть "**Custom repositories**".

3) У спливаючому вікні введіть наступну URL-адресу:

```
https://github.com/airalab/altruist-homeassistant-integration
```
4) Встановіть тип на "**Integration**" та натисніть "**ADD**".

{% roboWikiPicture {src:"docs/altruist/hacs.jpg", alt:"altruist-add"} %}{% endroboWikiPicture %}

5) Знайдіть інтеграцію **Altruist Sensor**.

6) Натисніть кнопку **Download**, потім перезапустіть **Home Assistant** після встановлення інтеграції.

{% roboWikiPicture {src:"docs/altruist/integration.jpg", alt:"altruist-hacs"} %}{% endroboWikiPicture %}

### Варіант 2: Ручне встановлення

1) Під користувачем `homeassistant`, клонувати репозиторій проекту:

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

3) Якщо у вас **немає** жодних користувацьких інтеграцій, перемістіть всю каталог custom_components:

{% codeHelper { copy: true}%}

 cd altruist-homeassistant-integration
mv custom_components/ ~/.homeassistant/

{% endcodeHelper %}

## Конфігурація

Після встановлення та перезапуску Home Assistant інтеграція автоматично виявить Altruist у вашій мережі.

1) Перейдіть до **Налаштування → Пристрої та Сервіси**.

2) Додайте **Датчик Altruist**.

{% roboWikiPicture {src:"docs/altruist/add_altruist.jpg", alt:"discover altruist"} %}{% endroboWikiPicture %}

Готово! 🚀 Ваш датчик Altruist тепер інтегровано з Home Assistant.