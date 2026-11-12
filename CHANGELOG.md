# سجل التغييرات

جميع التغييرات الملحوظة في هذا المشروع موثقة في هذا الملف وفق معيار [Keep a Changelog](https://keepachangelog.com/ar/1.0.0/)، ويلتزم المشروع بقواعد [Semantic Versioning](https://semver.org/).

## [2.4.3] - 2026-11-11

### حسّن
- **نقل عنوان الدرس وتثبيته في اللوحة السفلية + تفاعل تساقط الثمار** في [lessons-3d/index.html](file:///c:/wamp64/www/AR-lessons/lessons-3d/index.html):
  - إزالة شريط عنوان الدرس من الشريط العلوي وتثبيته كعنوان رئيسي دائم داخل مربع الأدوات السفلي (`الدرس 15 · سورة إبراهيم (24–26)`) بدلاً من العناوين المتغيرة للمراحل.
  - رفع مواضع ثمار التفاح إلى وسط وأعلى التاج الأخضر (`yFrac` 36%–78%) لظهور أوضح فوق الأغصان.
  - إضافة محاكاة فيزيائية متكاملة (`triggerFruitCascade`) لتساقط التفاح الناضج على قرص العشب مع ارتداد خفيف ثم تجدده تلقائياً في الأغصان عند الضغط على «تؤتي أكلها» أو لمس الثمار مباشرة على المجسم.
  - إصلاح ملف [lessons-3d/.htaccess](file:///c:/wamp64/www/AR-lessons/lessons-3d/.htaccess) (1,199 بايت) وإعادة بناء [lesson-3d-bundle.zip](file:///c:/wamp64/www/AR-lessons/lesson-3d-bundle.zip).

## [2.4.2] - 2026-11-11

### أصلح
- **تحسينات جراحية خفيفة في نسخة النشر [dist/](file:///c:/wamp64/www/AR-lessons/dist/)** مع الحفاظ الكامل على النخلة والألوان والأيقونات والأداء الأصلي:
  - ضبط مقاسات اللوحة السفلية (`.bottom-sheet`) برفع `max-height` إلى `min(380px, 44vh)` وتنسيق شبكة الأزرار الثلاثية (`repeat(3, minmax(0, 1fr))`) لمنع أي قص عمودي للأزرار.
  - إضافة ميزة **Play / Stop Toggle** (`▶` ↔ `■`) لمشغل الآيات القرآنية مع إيقاف التلاوة تلقائياً عند الانتقال بين المراحل أو إتمام الدرس.
  - إصلاح ملف [.htaccess](file:///c:/wamp64/www/AR-lessons/dist/.htaccess) (783 بايت) ومزامنة [ibrahim-parable-interactive.html](file:///c:/wamp64/www/AR-lessons/dist/ibrahim-parable-interactive.html) وإعادة بناء [lesson-bundle.zip](file:///c:/wamp64/www/AR-lessons/lesson-bundle.zip).

## [2.4.1] - 2026-11-11

### أصلح
- **تجميع الثمار وتلوينها كتفاح أحمر** في [lessons-3d/index.html](file:///c:/wamp64/www/AR-lessons/lessons-3d/index.html):
  - بناء دالة `computeExactVertexBox` لقياس رؤوس التاج الفعلية بدقة ومنع تبعثر الثمار خارج الشجرة.
  - تحويل الثمار إلى **تفاح أحمر لامع** (`0xd11924`) مع عُنق بني، وحصرها في قبة التاج الأخضر (18 تفاحة).
- **إلغاء الفجوة بين قاعدة الشجرة ومقطع التربة**:
  - محاذاة قرص العشب (`Base_Material.873_0`) مباشرة على سطح قاعدة التربة (`y = 0.012`) ومواءمة قطرها (`1.62`) ليتطابق مع أسطوانة التربة الشفافة والجذور العميقة بلا فراغ.
- **تصحيح أبعاد مستطيل التحكم السفلي**:
  - توسيع `max-height` إلى `min(380px, 44vh)` وضبط شبكة الأزرار الثلاثية لمنع قص أزرار الاستكشاف من الأعلى.

### حسّن
- **تطوير محرك الصوت والتلاوة التلقائية**:
  - استبدال صوت الصفارة عند الضغط على «تؤتي أكلها» بنغمة هادئة (`playSoftBloom`) مع عرض وتلاوة الآية 25 (﴿تُؤْتِي أُكُلَهَا كُلَّ حِينٍ...﴾) تلقائياً.
  - ترقية زر مشغل الآيات إلى **Play / Stop Toggle** حقيقي يوقف التلاوة ويعيد المؤشر للبداية مع تبديل أيقونة المثلث/المربع.
  - تشغيل الآية المخصصة لكل مرحلة تلقائياً عند الانتقال إليها أو عند تبديل الشجرة الطيبة والخبيثة.
- إعادة بناء أرشيف النشر المباشر [lesson-3d-bundle.zip](file:///c:/wamp64/www/AR-lessons/lesson-3d-bundle.zip).

## [2.4.0] - 2026-11-11

### أضيف
- **النسخة المستقلة المحسنة بنموذج GLB ثلاثي الأبعاد** في المجلد [lessons-3d/](file:///c:/wamp64/www/AR-lessons/lessons-3d/):
  - توظيف نموذج [`low_poly_tree.glb`](file:///c:/wamp64/www/AR-lessons/lessons-3d/assets/models/low_poly_tree.glb) مع مسار تحميل مزدوج يتراجع تلقائياً إلى [`low_poly_tree-inline.js`](file:///c:/wamp64/www/AR-lessons/lessons-3d/assets/models/low_poly_tree-inline.js) لدعم الفتح المباشر عبر `file://` والاسترداد الاحتياطي.
  - معالجة ألوان PBR عبر `THREE.ACESFilmicToneMapping` و `THREE.sRGBEncoding` وبيئة انعكاس سماوية (`PMREMGenerator`)، وضبط `depthWrite = true` لخامات الأوراق الشفافة.
  - عزل العناصر غير المرتبطة بالدرس (`Axe`, `Stump`, `Mushroom`, `Fungus`, `Plane.336`) ودمج قرص العشب الأصلي فوق مقطع التربة الشفاف والجذور العميقة.
  - المعايرة المكانية الديناميكية (`THREE.Box3`) لنشر 22 ثمرة متوهجة متنامية داخل التاج، وحركة موجية عضوية لطبقات الأوراق بالرياح.
  - تحسينات في الواجهة النهارية `Qahera UI`: تبديل تشغيل/إيقاف التلاوة بأيقونة SVG ديناميكية، وإغلاق نافذة المعلومات بزر `Escape`، وحالات `:focus-visible` كاملة.
  - ملف خادم [.htaccess](file:///c:/wamp64/www/AR-lessons/lessons-3d/.htaccess) لدعم `model/gltf-binary .glb` وأرشيف النشر المباشر [lesson-3d-bundle.zip](file:///c:/wamp64/www/AR-lessons/lesson-3d-bundle.zip).
- تحديث البوابة الرئيسية [index.html](file:///c:/wamp64/www/AR-lessons/index.html) ببطاقة تشغيل للنسخة الجديدة.

## [2.3.1] - 2026-11-11

### أضيف
- **تحويل النسخة النهارية إلى موقع مصغر مستقل بالكامل (Standalone Micro-website)**:
  - إزالة أي ارتباط بالمسارات الأبوية (`../`) لتمكين النشر على جذر النطاق أو داخل مجلد فرعي مستقل.
  - إضافة نافذة معلومات الدرس والجهة المطورة (`#modal-info`) مع زر وصول سريع في شريط التحكم العلوي.
  - إضافة شارة توثيق جهة التطوير والتصميم (`alwkala.com | الوكالة للأبحاث الرقمية`) في أسفل شاشتي الاستهلال والتهنئة.
  - إضافة وسوم البيانات الوصفية الكاملة (OpenGraph, Twitter Cards, Description, Theme Color, Canonical).
  - إضافة أيقونة موقع مدمجة (SVG Data-URI Favicon) دون الحاجة لملفات صور خارجية.
  - بناء ملف إعدادات خادم Apache مخصص [.htaccess](file:///c:/wamp64/www/AR-lessons/lessons-light/.htaccess) متضمناً ضغط الملفات وتخزين الأصول المؤقت وترويسات الأمان.
  - إنشاء أرشيف مضغوط جاهز للرفع المباشر [lesson-light-bundle.zip](file:///c:/wamp64/www/AR-lessons/lesson-light-bundle.zip) بحجم ~280 كيلوبايت.

### أصلح
- معالجة خطأ انقطاع الاتصال عند تشغيل التلاوة الصوتية بدون اتصال بشبكة الإنترنت مع إظهار إشعار بديل بدلاً من التوقف الصامت.

## [2.3.0] - 2026-11-11

### أضيف
- **نسخة النمط النهاري المستقلة بالكامل (Qahera UI Light Mode)** في المجلد [lessons-light/](file:///c:/wamp64/www/AR-lessons/lessons-light):
  - تطبيق رموز نظام التصميم **Qahera UI Kit** للألوان والأسطح الزجاجية النهارية المستوحاة من رمال الواحات ونور الصباح مع تباين قراءة معتمد (WCAG AAA/AA).
  - الالتزام التام بمعيار الأيقونات الصارم (`QAHERA-VISUAL-001`): إزالة كافة الإيموجيات واستبدالها بحزمة أيقونات فيكتور **SVG** مقاس 24x24 دقيقة وأنيقة (أيقونة الشجرة، الرياح، الهدف، التكريم، وأيقونات أدوات التحكم).
  - بيئة ثلاثية الأبعاد نهارية (Daylight Atmosphere): سماء طبيعية مشرقة، وإضاءة شمسية دافئة مع ضوء محيطي هادئ وخامات معدلة تمنع السطوع الزائد (Overexposure).
  - شاشة بداية وشاشة تهنئة نهارية بتصميم زجاجي ناصع.
  - إعدادات استضافة مخصصة [.htaccess](file:///c:/wamp64/www/AR-lessons/lessons-light/.htaccess) ودليل تشغيل [README.md](file:///c:/wamp64/www/AR-lessons/lessons-light/README.md).
- تحديث بوابة الدروس [index.html](file:///c:/wamp64/www/AR-lessons/index.html) لإضافة بطاقة تشغيل مباشرة للنسخة النهارية الجديدة.

## [2.2.0] - 2026-11-11

### أضيف
- **شاشة استهلالية وتمهيدية (Intro Screen)** قبل دخول الدرس:
  - ترويسة بهوية المقرر (التفسير ١ · الصف الأول الثانوي · سورة إبراهيم).
  - عنوان رئيسي بارز بخط **Tmanya Display** مع الآية المقررة بخط **Amiri Quran**.
  - بطاقات أهداف الدرس الثلاثة (استكشاف المثل · اختبار الريح · الاسترجاع النشط).
  - زر بدء الدرس («بدء الدرس») لتهيئة محرك الصوت وبدء المشهد ثلاثي الأبعاد بسلاسة.
- **شاشة تهنئة وإنجاز (Completion Screen)** تفتح عند إنهاء الطالب لمراحل الدرس:
  - وسام إنجاز وتهنئة بإتمام الدرس والتدبر.
  - شبكة إحصاءات الإنجاز (استكشاف 100% · اجتياز اختبار الريح · إتقان معاني المفردات 3/3).
  - بطاقة الأثر السلوكي والإيماني لثمرة الكلمة الطيبة في حياة المسلم.
  - أزرار سريعة وموجزة («إعادة» لإعادة الدرس، و«الرئيسية» للانتقال إلى بوابة الدروس).
- معزوفة نغمية احتفالية (Chime & Fanfare Arpeggio) عبر محرك Web Audio عند البدء والإتمام.
- **حزمة النشر الجاهزة للاستضافة (Production Bundle)** في المجلد [dist/](file:///c:/wamp64/www/AR-lessons/dist):
  - ملف [index.html](file:///c:/wamp64/www/AR-lessons/dist/index.html) كصفحة افتراضية للمشغل.
  - ملف [ibrahim-parable-interactive.html](file:///c:/wamp64/www/AR-lessons/dist/ibrahim-parable-interactive.html) للروابط المباشرة.
  - مكتبة [three.min.js](file:///c:/wamp64/www/AR-lessons/dist/three.min.js) محلياً.
  - خط [tmanya-display.otf](file:///c:/wamp64/www/AR-lessons/dist/tmanya-display.otf) محلياً.
  - ملف [.htaccess](file:///c:/wamp64/www/AR-lessons/dist/.htaccess) لإعدادات خوادم الويب وضبط الـ MIME types وضغط الملفات.
  - دليل النشر [README.md](file:///c:/wamp64/www/AR-lessons/dist/README.md).
  - أرشيف مضغوط جاهز للرفع بنقرة واحدة [lesson-bundle.zip](file:///c:/wamp64/www/AR-lessons/lesson-bundle.zip) بحجم ~295 كيلوبايت.

### أصلح
- **إعادة ضبط الكاميرا والتأطير الذكي الشامل**:
  - قياس ديناميكي دقيق لأبعاد العناصر الحقيقية عبر DOM Bounding Rects لمنع أي تداخل.
  - تصحيح مركز المجسم الرأسي وهامش الأمان (Safety Factor) لاحتواء كامل النخلة من مقطع التربة والجذور إلى أعلى السعف على الهواتف والشاشات العريضة.
  - إضافة زاوية ميل علوية خفيفة (Tilt ~7°) لإبراز عمق التربة والجذور وعراجين الرطب ثلاثية الأبعاد.

## [2.1.4] - 2026-11-11

### أضيف
- دمج خط **Tmanya Display** المحلي ([tmanya-display.otf](file:///c:/wamp64/www/AR-lessons/lessons/tmanya-display.otf)) عبر `@font-face` وتطبيقه على العناوين الرئيسية والهوية في:
  - صفحة الدرس التفاعلي [ibrahim-parable-interactive.html](file:///c:/wamp64/www/AR-lessons/lessons/ibrahim-parable-interactive.html).
  - بوابة مشغل الدروس [index.html](file:///c:/wamp64/www/AR-lessons/index.html).
- ترقية المنظومة الطباعية وفق معايير **Qahera UI**:
  - خط **Tmanya Display** للعناوين الرئيسية والهوية والبطاقات البارزة.
  - خط **Alexandria** للأزرار والملصقات المكانية والشارات.
  - خط **IBM Plex Sans Arabic** للنصوص والأسئلة والخيارات التفاعلية.
  - خط **Amiri Quran** للآيات الكريمة في شريط التلاوة.

## [2.1.3] - 2026-11-11

### أضيف
- دمج خطوط Google Fonts (Alexandria و IBM Plex Sans Arabic و Amiri Quran).

## [2.1.2] - 2026-11-11

### أصلح
- تصحيح معادلة الكاميرا والتأطير في [ibrahim-parable-interactive.html](file:///c:/wamp64/www/AR-lessons/lessons/ibrahim-parable-interactive.html).
- تحويل اللوحة السفلية إلى بطاقة عائمة مدمجة (Floating Dock) بحواف دائرية بارتفاع أقصى 28vh فقط.
- إضافة ميزة التكبير والتصغير التفاعلي بعجلة الفأرة واللمس المتعدد (Pinch-to-zoom).

## [2.1.1] - 2026-11-11

### أصلح
- ضبط عدسة الكاميرا وحساب المسافة التلقائية (`optimalDist`).
- إعادة بناء سعف النخلة (24 سعفة بـ 3 طبقات: القلب، السعف الأوسط، والسعف المتدلي).
- إعادة تشكيل عراجين الرطب بأغصان مقوسة وثمار بيضاوية.
- إبراز مقطع التربة الشفاف مع الجذور العميقة.

## [2.1.0] - 2026-11-11

### أضيف
- بوابة مشغل الدروس التفاعلية [index.html](file:///c:/wamp64/www/AR-lessons/index.html).

## [2.0.0] - 2026-11-11

### أضيف
- ملف الدرس التفاعلي المنهجي [ibrahim-parable-interactive.html](file:///c:/wamp64/www/AR-lessons/lessons/ibrahim-parable-interactive.html).

## [1.0.0] - 2026-11-11

### أضيف
- النموذج الأولي للدرس [ibrahim-parable-ar-prototype.html](file:///c:/wamp64/www/AR-lessons/lessons/ibrahim-parable-ar-prototype.html).
