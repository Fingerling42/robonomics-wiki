---
title: 1 Груповий Розумний Вимикач
contributors: [nakata5321]
---
Ця стаття покаже вам процес налаштування 1 Групового Розумного Вимикача.

{% roboWikiNote {type: "warning"}%}Усі пристрої від Robonomics можна придбати на офіційному [веб-сайті](https://robonomics.network/devices/).{% endroboWikiNote %}

{% roboWikiVideo {videos:[{src: 'QmTWhDu1PdQgR1ZuLuGpEtYG8uMm8eiWLziK1zLupQwU2i', type: 'mp4'}], attrs:['loop', 'controls', 'autoplay']} %}{% endroboWikiVideo %}

{% roboWikiTitle { type:'2', anchor: 'step1'} %} Крок 1 — Прошивка {% endroboWikiTitle %}

{% roboWikiNote {type: "warning"}%}Усі пристрої від Robonomics поставляються з попередньою прошивкою. Однак, оскільки всі пристрої є наборами для розробки, інструкція охоплюватиме опцію прошивки пристрою з нуля. Якщо ви не бажаєте цього робити зараз, перейдіть до [**Крок 2 - Точка доступу**](/docs/ir-controller/#step2).
{% endroboWikiNote %}

Вийміть пристрій з коробки та підключіть його до комп'ютера. Потім перейдіть на веб-сайт [webflasher.robonomics.network](https://webflasher.robonomics.network/). Це веб-прошивальник.

{% roboWikiVideo {videos:[{src: 'QmVWmGSnvGwQ3dQfZC8iM5KHBoGpaWVXXUjNuNesULQrGw', type: 'mp4'}], attrs:['loop', 'controls', 'autoplay']} %}{% endroboWikiVideo %}

{% roboWikiNote {type: "warning"}%}Увага! Веб-прошивальник працює тільки з браузерами Google Chrome або Microsoft Edge.{% endroboWikiNote %}

У випадаючому списку "Firmware" оберіть опцію **"SWS-1G-E-11-23"**, а потім у "SELECT CHIP" оберіть **"ESP32"**. Натисніть кнопку **"CONNECT"**.
З'явиться спливаюче вікно, де ви повинні вибрати послідовний порт, до якого підключений пристрій (зазвичай це `/ttyUSB0`). Потім оберіть **"INSTALL SWS-1G-E-11-23"**.
На наступному вікні ви можете зробити **CLEAR INSTALLATION**, позначивши **ERASE DEVICE**. Натисніть Next, а потім Install. Зачекайте, поки прошивка завантажиться на пристрій Розумного вимикача.

Після завершення процесу встановлення, з'явиться спливаюче вікно конфігурації Wi-Fi. Введіть дані для підключення до Wi-Fi.

Після налаштування Wi-Fi ви можете відвідати пристрій за допомогою кнопки **VISIT DEVICE**. Пізніше ви можете відвідати пристрій за його IP-адресою в мережі. Щоб знайти його, ви можете використовувати [мобільний додаток Fing](https://www.fing.com/products) або [інструмент командного рядка nmap](https://vitux.com/find-devices-connected-to-your-network-with-nmap/).

Пропустіть **Крок 2 — Точка доступу** і перейдіть до [**Крок 3 — Конфігурація**](/docs/ir-controller/#step3).

{% roboWikiTitle { type:'2', anchor: 'step2'} %} Крок 2 — Точка доступу {% endroboWikiTitle %}

Якщо ви виймете Розумний вимикач з коробки та підключите його до джерела живлення, він створить точку доступу з назвою "robonomics-XXXXXXX". Підключіться до неї.
Повинно відкритися вікно конфігурації. Якщо цього не сталося, відкрийте веб-браузер та перейдіть на сторінку `192.168.4.1`.

{% roboWikiPicture {src:"docs/ir-controller/phone-wifi.jpg", alt:"image"} %}{% endroboWikiPicture %}

Введіть дані для підключення до Wi-Fi. Після цього пристрій Розумного вимикача підключиться до мережі Wi-Fi. Перевірте пристрій за його IP-адресою в мережі. Щоб знайти його, ви можете використовувати [мобільний додаток Fing](https://www.fing.com/products) або [інструмент командного рядка nmap](https://vitux.com/find-devices-connected-to-your-network-with-nmap/).

{% roboWikiTitle { type:'2', anchor: 'step3'} %} Крок 3 — Конфігурація {% endroboWikiTitle %}

{% roboWikiVideo {videos:[{src: 'QmZokF8TnReLt4B6q8ixkBmpZwpiiU9PQCPdyJw9RcnYFn', type: 'mp4'}], attrs:['loop'], cover: "cover-3.png"} %}{% endroboWikiVideo %}

Перейдіть до **"Configuration"**->**"Configure other"**. У рядку **"Template"** вставте наступне:

{% codeHelper { copy: true}%}

```shell
{"NAME":"Robonomics-1L-Switch","GPIO":[1,1,1,1,1,1,1,1,1,576,1,1,1,1,3200,5440,0,1,224,1,0,0,320,1,0,0,0,0,1,1,1,32,1,0,0,1],"FLAG":0,"BASE":1}
```

{% endcodeHelper %}

Переконайтеся, що прапорці **"Activate"** та **"MQTT Enable"** увімкнені. Якщо ні, увімкніть їх та натисніть кнопку Save.

Поверніться до головного меню та перейдіть до **"Configuration"** -> **"Configure MQTT"**.
Введіть свої дані для MQTT тут:

{% roboWikiPicture {src:"docs/ir-controller/mqtt.jpg", alt:"image"} %}{% endroboWikiPicture %}

Це все що стосується ESP наразі. Наступним кроком буде встановлення інтеграції з Home Assistant.

{% roboWikiTitle { type:'2', anchor: 'step4'} %} Крок 4 — Налаштування інтеграції {% endroboWikiTitle %}

Ця стаття передбачає, що у вас є Home Assistant. Щоб підключити пристрій Розумного вимикача до Home Assistant, вам потрібно встановити інтеграцію Tasmota.

{% roboWikiVideo {videos:[{src: 'QmQw6aA5e7UqT1hZrAV8m1UPq1rWCgLsWcVufuxitQm84p', type: 'mp4'}], attrs:['loop', 'controls', 'autoplay']} %}{% endroboWikiVideo %}

Зазвичай Home Assistant автоматично виявить інтеграцію Tasmota. Але якщо цього не сталося, додайте її вручну.
Це все. Тепер ви можете додати елемент вимикача на панель приладів.

{% roboWikiNote {type: "warning"}%}Усі пристрої від Robonomics можна придбати на офіційному [веб-сайті](https://robonomics.network/devices/).
{% endroboWikiNote %}