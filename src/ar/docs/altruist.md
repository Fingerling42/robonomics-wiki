---
title: إعداد Altruist
contributors: [tubleronchik]
---

**يرشدك هذا الدليل خلال إعداد وتفعيل مستشعر Altruist Outdoor. ستقوم بتوصيل المستشعر بشبكة Wi-Fi، وتكوين موقعه، وتفعيل اشتراك باستخدام رموز XRT. بالإضافة إلى ذلك، يتم توفير تعليمات لدمج المستشعر مع Home Assistant عبر HACS أو التثبيت اليدوي.**

{% roboWikiNote {type: "warning"}%} يمكن شراء جميع الأجهزة من Robonomics على [الموقع الرسمي](https://robonomics.network/devices/).{% endroboWikiNote %}

## تفعيل اشتراك Robonomics

{% roboWikiNote {type: "okay"} %}لإكمال هذه الخطوة، تأكد من أن لديك على الأقل 2-3 رموز XRT في حسابك `Robonomics Polkadot`.{% endroboWikiNote %}

1) انتقل إلى [صفحة الاشتراك](https://robonomics.app/#/rws-buy) في تطبيق Robonomics dApp.
2) انقر على **الحساب** وقم بتوصيل محفظتك. سيتم عرض عنوان حسابك ورصيدك.
إذا لم يكن لديك حساب، اتبع [هذا الدليل](https://wiki.robonomics.network/docs/create-account-in-dapp/) لإنشاء واحد.

{% roboWikiPicture {src:"docs/altruist/altruist_syb_buy.jpg", alt:"صفحة الاشتراك"} %}{% endroboWikiPicture %}

3) انقر على `شراء الاشتراك` ووقع المعاملة. **انتظر حتى تكتمل عملية التفعيل**.
4) بمجرد التفعيل، سيتم توجيهك إلى **صفحة الإعداد**، حيث يمكنك رؤية اسم اشتراكك وتاريخ انتهاء صلاحيته.

{% roboWikiPicture {src:"docs/altruist/altruist_setup_page.jpg", alt:"صفحة إعداد الاشتراك"} %}{% endroboWikiPicture %}

5) **احفظ عنوان حسابك** — ستحتاج إليه أثناء إعداد المستشعر. يمكنك نسخه من قسم "OWNER" أو بالنقر على اسم حسابك في الزاوية العلوية اليمنى واختيار زر النسخ.

## إعداد المستشعر

{% roboWikiNote {type: "warning", title: "معلومة"}%} يمكن توصيل المستشعر فقط بشبكة Wi-Fi بتردد 2.4GHz.{% endroboWikiNote %}

1) **قم بتوصيل المستشعر** بمقبس الطاقة.
2) ستقوم اللوحة بإنشاء شبكة Wi-Fi باسم Altruist-xxxxxxxxx. اتصل بها من هاتفك أو جهاز الكمبيوتر الخاص بك. يجب أن يتم توجيهك تلقائيًا لفتح نافذة التفويض.
- إذا لم يحدث ذلك، افتح المتصفح وانتقل إلى 192.168.4.1.

{% roboWikiPicture {src:"docs/altruist/networks.png", alt:"مستشعر-المحسن"} %}{% endroboWikiPicture %}

3) **قم بتكوين إعدادات Wi-Fi**:
- اختر شبكتك من القائمة أو أدخلها يدويًا إذا لم تظهر.
- أدخل كلمة المرور في حقل "إعدادات Wi-Fi".
- إذا كان لديك أجهزة Altruist متعددة على نفس الشبكة، قم بتغيير اسم المضيف المحلي. بعد إعداد WiFi، يمكنك الاتصال بمستشعرك باستخدام هذا الاسم.

{% roboWikiPicture {src:"docs/altruist/wifi_creds.png", alt:"مستشعر-المحسن"} %}{% endroboWikiPicture %}

4) **احفظ التكوين**
- انقر على `حفظ التكوين وإعادة التشغيل` وانتظر حتى يتصل المستشعر بشبكة WiFi. بمجرد الاتصال، سيعرض عنوان IP الجديد الخاص به - قم بنسخه، حيث أن هذه طريقة بديلة للاتصال بمستشعرك بعد الإعداد.

{% roboWikiPicture {src:"docs/altruist/connected.png", alt:"altruist-sensor"} %}{% endroboWikiPicture %}

5) **أدخل تفاصيل Robonomics الخاصة بك**:
- افتح واجهة الويب Altruist على http://altruist.local (أو استخدم اسم المضيف المحلي المخصص الخاص بك متبوعًا بـ `.local` إذا قمت بتغييره). ثم، انتقل إلى صفحة `التكوين`.
- في قسم `Robonomics`، الصق عنوان مالك RWS الذي قمت بنسخه سابقًا في الحقل المخصص.

6) **حدد موقع المستشعر**:
- في قسم `تصحيح GPS ودرجة الحرارة`، أدخل إحداثيات موقع تركيب المستشعر.
- يمكنك العثور على الإحداثيات باستخدام الخرائط عبر الإنترنت أو تحويل عنوان إلى خط العرض/الطول باستخدام [هذا الرابط.](https://www.latlong.net/convert-address-to-lat-long.html)

{% roboWikiNote {type: "warning", title: "تحذير"}%}سيتم عرض إحداثيات المستشعر بعد ذلك على خريطة متاحة للجمهور. إذا كنت لا ترغب في إظهار معلوماتك الخاصة، فاكتب إحداثيات قريبة ولكن ليست دقيقة.{% endroboWikiNote %}

{% roboWikiPicture {src:"docs/altruist/robo-gps.png", alt:"altruist-sensor-wifi"} %}{% endroboWikiPicture %}

7) **انسخ "عنوان Robonomics" الخاص بـ Altruist**:
- ستجده في أعلى الصفحة. احفظه لـالخطوة النهائية.

{% roboWikiPicture {src:"docs/altruist/address.jpg", alt:"عنوان المحسن"} %}{% endroboWikiPicture %}

8) انقر على "**حفظ التكوين وإعادة التشغيل**" في أسفل الصفحة. سيعاد تشغيل اللوحة.

## تفعيل المحسن
الخطوة النهائية في عملية الإعداد هي إضافة **عنوان المحسن** إلى **اشتراك روبونوميكس** الخاص بك.

1) ارجع إلى [صفحة الإعداد](https://robonomics.app/#/rws-setup).

2) قم بالتمرير لأسفل إلى قسم "**المستخدمون في الاشتراك**".

3) في حقل "**إضافة مستخدم**"، الصق **عنوان روبونوميكس المحسن** الذي نسخته سابقًا.

{% roboWikiPicture {src:"docs/altruist/add_user.jpg", alt:"إضافة مستخدم"} %}{% endroboWikiPicture %}

4) انقر على **زر الزائد (+)** ووقع الرسالة.

5) انتظر حتى تكتمل العملية.

هذا كل شيء! لقد اكتمل إعدادك الآن. 🎉

يمكنك الآن العثور على المحسن الخاص بك على خريطة [Robonomics Sensors Social](https://sensors.social/#). 🚀

{% roboWikiPicture {src:"docs/altruist/map.jpg", alt:"خريطة المستشعر"} %}{% endroboWikiPicture %}

## مساعد المنزل

هناك طريقتان لإضافة **المحسن** إلى **مساعد المنزل**:

### الخيار 1: HACS (موصى به)

أسهل طريقة لإضافة **المحسن** هي من خلال **HACS**. يمكنك العثور على دليل إعداد مختصر [هنا](https://hacs.xyz/docs/use/) 

**الخطوات****:
1) بمجرد تثبيت HACS، افتحه.

2) انقر على **النقاط الثلاث** في الزاوية العلوية اليمنى واختر "**مستودعات مخصصة**".

3) في النافذة المنبثقة، أدخل عنوان URL التالي:

```
https://github.com/airalab/altruist-homeassistant-integration
```
4) حدد النوع على أنه "**تكامل**" وانقر على "**إضافة**".

{% roboWikiPicture {src:"docs/altruist/hacs.jpg", alt:"altruist-add"} %}{% endroboWikiPicture %}

5) ابحث عن تكامل **Altruist Sensor**.

6) انقر على زر **تنزيل**، ثم أعد تشغيل **Home Assistant** بمجرد تثبيت التكامل.

{% roboWikiPicture {src:"docs/altruist/integration.jpg", alt:"altruist-hacs"} %}{% endroboWikiPicture %}

### الخيار 2: التثبيت اليدوي

1) تحت المستخدم `homeassistant`، استنسخ مستودع المشروع:

{% codeHelper { copy: true}%}

```shell
  git clone https://github.com/airalab/altruist-homeassistant-integration.git
```

{% endcodeHelper %}

2) إذا كان لديك بالفعل أي تكاملات مخصصة، انقل مجلد `altruist` إلى دليل `custom_components` الخاص بك:

{% codeHelper { copy: true}%}

```
cd altruist-homeassistant-integration
mv custom_components/altruist ~/.homeassistant/custom_components/
```

{% endcodeHelper %}

3) إذا **لم** يكن لديك أي تكاملات مخصصة، انقل دليل custom_components بالكامل:

{% codeHelper { copy: true}%}

 ```
cd altruist-homeassistant-integrationmv custom_components/ ~/.homeassistant/
```

{% endcodeHelper %}

## التكوين

بعد التثبيت وإعادة تشغيل Home Assistant، سيقوم التكامل بالكشف تلقائيًا عن Altruist على شبكتك.

1) اذهب إلى **الإعدادات → الأجهزة والخدمات**.

2) أضف **مستشعر Altruist**.

{% roboWikiPicture {src:"docs/altruist/add_altruist.jpg", alt:"اكتشاف Altruist"} %}{% endroboWikiPicture %}

هذا كل شيء! 🚀 تم الآن دمج مستشعر Altruist مع Home Assistant.