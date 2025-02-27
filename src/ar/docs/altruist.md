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

3) انقر على `BUY SUBSCRIPTION` ووقع المعاملة. **انتظر حتى يكتمل عملية التفعيل**.
4) بمجرد التفعيل، سيتم توجيهك إلى **صفحة الإعداد**، حيث يمكنك رؤية اسم اشتراكك وتاريخ انتهاء صلاحيته.

{% roboWikiPicture {src:"docs/altruist/altruist_setup_page.jpg", alt:"صفحة إعداد الاشتراك"} %}{% endroboWikiPicture %}

5) **احفظ عنوان حسابك** — ستحتاج إليه أثناء إعداد المستشعر. يمكنك نسخه من قسم "OWNER" أو بالنقر على اسم حسابك في الزاوية العلوية اليمنى واختيار زر النسخ.

## إعداد المستشعر

{% roboWikiNote {type: "warning", title: "معلومات"}%} يمكن توصيل المستشعر فقط بشبكة Wi-Fi بتردد 2.4GHz.{% endroboWikiNote %}

1) **قم بتوصيل المستشعر** بمقبس الطاقة.
2) ستقوم اللوحة بإنشاء شبكة Wi-Fi باسم Altruist-xxxxxxxxx. اتصل بها من هاتفك أو جهاز الكمبيوتر الخاص بك. يجب أن يتم توجيهك تلقائيًا لفتح نافذة التفويض.
- إذا لم يحدث ذلك، افتح متصفحًا وانتقل إلى 192.168.4.1.

{% roboWikiPicture {src:"docs/altruist/on_board.png", alt:"مستشعر-الخير"} %}{% endroboWikiPicture %}

3) **قم بتكوين إعدادات Wi-Fi**:
- اختر شبكتك من القائمة أو أدخلها يدويًا إذا لم تظهر.
- أدخل كلمة المرور في حقل "إعدادات Wi-Fi".

4) **أدخل تفاصيل Robonomics الخاصة بك**:
- الصق عنوان مالك RWS الذي نسخته سابقًا في الحقل المخصص.

5) **حدد موقع المستشعر**:
- أدخل إحداثيات موقع تركيب المستشعر.
- يمكنك العثور على الإحداثيات باستخدام الخرائط عبر الإنترنت أو تحويل عنوان إلى خط عرض/طول باستخدام [هذا الرابط.](https://www.latlong.net/convert-address-to-lat-long.html)

{% roboWikiNote {type: "warning", title: "تحذير"}%}سيتم عرض إحداثيات المستشعر بعد ذلك على خريطة متاحة للجمهور. إذا كنت لا ترغب في عرض معلوماتك الخاصة، فاكتب إحداثيات قريبة ولكن غير دقيقة.{% endroboWikiNote %}

{% roboWikiPicture {src:"docs/altruist/sensor_setup.png", alt:"altruist-sensor-wifi"} %}{% endroboWikiPicture %}

6) **انسخ "عنوان روبونوميكس" الخاص بـ Altruist**:
- ستجده في أعلى الصفحة. احفظه للخطوة النهائية.

{% roboWikiPicture {src:"docs/altruist/address.jpg", alt:"altruist address"} %}{% endroboWikiPicture %}

7) انقر على "**حفظ التكوين وإعادة التشغيل**" في أسفل الصفحة. ستعيد اللوحة التشغيل وتتصل بشبكة Wi-Fi المحددة.

## تفعيل Altruist
الخطوة النهائية في عملية الإعداد هي إضافة **عنوان Altruist** إلى **اشتراك روبونوميكس** الخاص بك.

1) ارجع إلى [صفحة الإعداد](https://robonomics.app/#/rws-setup).

2) قم بالتمرير لأسفل إلى قسم "**المستخدمون في الاشتراك**".

3) في حقل "**إضافة مستخدم**"، الصق **عنوان روبونوميكس Altruist** الذي نسخته سابقًا.

{% roboWikiPicture {src:"docs/altruist/add_user.jpg", alt:"add user"} %}{% endroboWikiPicture %}

4) انقر على **زر الزائد (+)** ووقع الرسالة.

5) انتظر حتى تكتمل العملية.

هذا كل شيء! إعدادكاكتمل الآن. 🎉

يمكنك الآن العثور على Altruist الخاص بك على خريطة [Robonomics Sensors Social](https://sensors.social/#). 🚀

{% roboWikiPicture {src:"docs/altruist/map.jpg", alt:"خريطة المستشعر"} %}{% endroboWikiPicture %}

## مساعد المنزل

هناك طريقتان لإضافة **Altruist** إلى **مساعد المنزل**:

### الخيار 1: HACS (موصى به)

أسهل طريقة لإضافة **Altruist** هي من خلال **HACS**. يمكنك العثور على دليل إعداد مختصر [هنا](https://hacs.xyz/docs/use/)

**الخطوات**:
1) بمجرد تثبيت HACS، افتحه.

2) انقر على **النقاط الثلاث** في الزاوية العلوية اليمنى وحدد "**المستودعات المخصصة**".

3) في النافذة المنبثقة، أدخل عنوان URL التالي:

```
https://github.com/airalab/altruist-homeassistant-integration
```
4) قم بتعيين النوع إلى "**تكامل**" وانقر على "**إضافة**".

{% roboWikiPicture {src:"docs/altruist/hacs.jpg", alt:"إضافة altruist"} %}{% endroboWikiPicture %}

5) ابحث عن تكامل **مستشعر Altruist**.

6) انقر على زر **تنزيل**، ثم أعد تشغيل **مساعد المنزل** بمجرد تثبيت التكامل.

{% roboWikiPicture {src:"docs/altruist/integration.jpg", alt:"altruist-hacs"} %}{% endroboWikiPicture %}

### الخيار 2: التثبيت اليدوي

1) تحت المستخدم `homeassistant`، قم باستنساخ مستودع المشروع:

{% codeHelper { copy: true}%}

```shell
  git clone https://github.com/airalab/altruist-homeassistant-integration.git
```

{% endcodeHelper %}

2) إذا كان لديك أي تكاملات مخصصة بالفعل، انقل مجلد `altruist` إلى دليل `custom_components` الخاص بك:

{% codeHelper { copy: true}%}

```
cd altruist-homeassistant-integration
mv custom_components/altruist ~/.homeassistant/custom_components/
```

{% endcodeHelper %}

3) إذا كنت **لا** تملك أي تكاملات مخصصة، انقل دليل custom_components بالكامل:

{% codeHelper { copy: true}%}

 ```
cd altruist-homeassistant-integration
mv custom_components/ ~/.homeassistant/
```

{% endcodeHelper %}

## التكوين

بعد التثبيت وإعادة تشغيل Home Assistant، سيكتشف التكامل تلقائيًا Altruist على شبكتك.

1) اذهب إلى **الإعدادات → الأجهزة والخدمات**.

2) أضف **مستشعر Altruist**.

{% roboWikiPicture {src:"docs/altruist/add_altruist.jpg", alt:"اكتشاف altruist"} %}{% endroboWikiPicture %}

هذا كل شيء! 🚀 تم الآن دمج مستشعر Altruist مع Home Assistant.