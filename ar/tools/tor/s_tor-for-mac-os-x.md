---
index: 18
title: تور لنظام التشغيل Mac OS X
---
# دليل أدوات TOR لنظام التشغيل MAC 

** درس القراءة: [الإنترنت](umbrella://communications/the-internet) **
** يوضح هذا الدليل كيفية استخدام [حزمة متصفح تور] https://www.torproject.org/projects/torbrowser.html.en) على نظام Mac. **
** متطلبات الكمبيوتر: ** اتصال بالإنترنت ، جهاز كمبيوتر يعمل بنظام macOS
** الإصدار المستخدم في هذا الدليل: ** حزمة متصفح Tor: 3.6.2
** الترخيص: ** البرمجيات المجانية ؛ مزيج من تراخيص البرمجيات المجانية
** المستوى: ** متوسط
** قراءة أخرى: **[https://tor.stackexchange.com/](https://tor.stackexchange.com/) 
الوقت اللازم:
 15-30 دقيقة

** سوف يمنحك استخدام Tor: **
- القدرة على الالتفاف على الرقابة على الإنترنت
- القدرة على الحصول على الانترنت بشكل مجهول

### 1.0 قبل البدء

تور هي خدمة تطوعية تعمل على توفير الخصوصية وإخفاء الهوية عبر الإنترنت من خلال إخفاء شخصيتك ومكان الاتصال. كما تقوم الخدمة بحمايتك من شبكة Tor نفسها.

بالنسبة للأشخاص الذين قد يحتاجون إلى إخفاء الهوية والخصوصية في بعض الأحيان عند الوصول إلى مواقع الويب ، يوفر متصفح Tor طريقة سريعة وسهلة لاستخدام شبكة Tor.

أسهل طريقة لاستخدام شبكة Tor هي استخدام Tor Browser Bundle ، الذي يجمع بين متصفح الويب وبرنامج Tor والبرامج المساعدة الأخرى التي ستمنحك طريقة أكثر أمانًا للدخول إلى الويب.

**يعمل متصفح Tor تمامًا مثل متصفحات الويب الأخرى ، باستثناء أنه يرسل اتصالاتك عبر تور ، مما يجعل من الصعب على الأشخاص الذين يراقبونك معرفة ما تفعله على الإنترنت بالضبط ، ويصعب على الأشخاص الذين يراقبون المواقع التي تستخدمها. تعرف على المكان الذي تتصل منه. ضع في اعتبارك أن الأنشطة التي تقوم بها داخل Tor Browser فقط ستكون مجهولة المصدر. إن وجود Tor Browser مثبت على جهاز الكمبيوتر الخاص بك لا يجعل الأشياء التي تقوم بها على نفس الكمبيوتر باستخدام برامج أخرى (مثل متصفح الويب العادي) مجهولة. **

# 2.0 الحصول على حزمة متصفح Tor

افتح متصفحًا مثل Mozilla Firefox أو Internet Explorer واكتب: 
[https://www.torproject.org/projects/torbrowser.html.en] من (https://www.torproject.org/projects/torbrowser.html.en) في شريط URL. إذا كنت تستخدم محرك بحث للبحث عن حزمة متصفح Tor ، فتأكد من صحة عنوان URL
 ![صورة](tool_torosx1.jpeg)

انقر فوق زر التحميل الأرجواني الكبير للحصول على برنامج التثبيت لـ Tor Browser Bundle.
![صورة](tool_torosx2.jpeg)

سيكتشف موقع الويب نظام التشغيل الخاص بك وستحصل على الملف الصحيح لـ Windows. إذا كنت تريد ، لأي سبب ، ملف مثبت مختلف ، فيمكنك التمرير لأسفل إلى قسم تنزيلات متصفح Tor.
![صورة](tool_torosx3.jpeg)

سيطلب منك العديد من المتصفحات تأكيد ما إذا كنت تريد تنزيل هذا الملف.

بالنسبة لأي متصفح ، من الأفضل حفظ الملف أولاً قبل المتابعة. لذلك انقر فوق الزر "حفظ".

### 2.1 تثبيت حزمة متصفح Tor

بعد اكتمال التنزيل ، قد تحصل على خيار لفتح المجلد الذي تم تنزيل الملف إليه. الموقع الافتراضي هو مجلد التنزيلات.

انقر نقرًا مزدوجًا فوق مثبت Tor Browser. هذا يفتح ملف .dmg.

(في الإصدارات الحديثة من نظام MacOS ، قد تحصل على تحذير بأن "مطور مجهول الهوية" - يمكنك الالتفاف حول هذه الشكوى عن طريق التحكم بالضغط واختيار "فتح".)

اسحب الملف المضمن إلى مجلد التطبيقات لديك وسيكون لديك تطبيق Tor Browser باللغة التي اخترتها والتي يمكنك تثبيتها على Dock.
![صورة](tool_torosx4.png)

** بدء تشغيل متصفح Tor للمرة الأولى **

افتح مجلد Tor Browser من مجلد التطبيقات الخاص بك وانقر مرتين على الملف المسمى Tor Browser.

عند تشغيل متصفح Tor لأول مرة ، قد تحصل على نافذة تسمح لك بتعديل بعض الإعدادات إذا لزم الأمر. قد تضطر إلى العودة وتغيير بعض إعدادات التكوين ، ولكن عليك أن تحاول الاتصال بشبكة Tor بالنقر فوق الزر Connect.

بعد النقر على زر الاتصال ، سيتم فتح نافذة جديدة بشريط أخضر أطول بمرور الوقت الذي يبدأ فيه برنامج Tor.
![صورة](tool_torosx5.jpeg)

عند بدء تشغيل متصفح Tor للمرة الأولى ، قد يستغرق الأمر وقتًا أطول قليلاً من المعتاد ، ولكن كن صبورًا ، في غضون بضع دقائق سيتم تشغيل متصفح Tor وسيفتح متصفح الويب مهنئاً لك.
![صورة](tool_torosx6.jpeg)