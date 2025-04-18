# AdGuardPrivate

AdGuardPrivate هو فرع من _AdGuardHome_، مصمم لتقديم نسخة مستضافة على SaaS مع ميزات محسنة وقابلية للتخصيص. يتم استضافته على [AdGuard Private](https://adguardprivate.com).

## الميزات الرئيسية

### الميزات الأصلية

1. **حظر الإعلانات على مستوى الشبكة**

   - يحظر الإعلانات والمتعقبين عبر جميع الأجهزة في شبكتك.
   - يعمل كخادم DNS يعيد توجيه نطاقات التتبع إلى "حفرة سوداء".

2. **قواعد التصفية المخصصة**

   - أضف قواعد تصفية مخصصة خاصة بك.
   - راقب وتحكم في نشاط الشبكة.

3. **دعم DNS المشفر**

   - يدعم DNS-over-HTTPS، DNS-over-TLS، وDNSCrypt.

4. **خادم DHCP المدمج**

   - يوفر وظائف خادم DHCP جاهزة للاستخدام.

5. **تكوين لكل عميل**

   - قم بتكوين الإعدادات للأجهزة الفردية.

6. **الرقابة الأبوية**

   - يحظر نطاقات البالغين ويفرض البحث الآمن على محركات البحث.

7. **التوافق متعدد المنصات**

   - يعمل على Linux، macOS، Windows، وغيرها.

8. **مركز على الخصوصية**
   - لا يجمع إحصاءات الاستخدام أو يرسل بيانات ما لم يتم تكوينه صراحة.

### الميزات الجديدة من AdGuardPrivate

1. **توجيه DNS باستخدام قوائم القواعد**

   - قم بتخصيص توجيه DNS باستخدام قوائم القواعد المحددة في ملف التكوين.
   - يدعم قواعد الطرف الثالث مثل [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat).

2. **قوائم قواعد حظر مخصصة للتطبيقات**

   - قم بتكوين حظر المصادر من تطبيقات معينة.
   - يدعم تكوينات الطرف الثالث لإدارة مرنة.

3. **DNS الديناميكي (DDNS)**

   - يوفر قدرات حل اسم النطاق الديناميكي لسيناريوهات متنوعة.

4. **تحديد السرعة المتقدم**

   - ينفذ تدابير إدارة وتحكم في حركة المرور بكفاءة.

5. **ميزات النشر المحسنة**
   - دعم توازن الحمل.
   - صيانة الشهادات التلقائية.
   - تحسين اتصالات الشبكة.

للوثائق التفصيلية، تفضل بزيارة: [وثائق AdGuardPrivate](https://adguardprivate.com/docs/)

## كيفية الاستخدام

### تحميل النسخة الثنائية

يمكنك تحميل النسخة الثنائية مباشرة من صفحة [الإصدارات](https://github.com/AdGuardPrivate/AdGuardPrivate/releases). بعد التحميل، اتبع الخطوات التالية لتشغيلها:

```bash
./AdGuardPrivate -c ./AdGuardHome.yaml -w ./data --web-addr 0.0.0.0:34020 --local-frontend --no-check-update --verbose
```

### استخدام صورة Docker

بدلاً من ذلك، يمكنك استخدام صورة Docker المتاحة على [Docker Hub](https://hub.docker.com/repository/docker/adguardprivate/adguardprivate):

```bash
docker run --rm --name AdGuardPrivate -p 34020:80 -v ./data/container/work:/opt/adguardhome/work -v ./data/container/conf:/opt/adguardhome/conf adguardprivate/adguardprivate:latest
```