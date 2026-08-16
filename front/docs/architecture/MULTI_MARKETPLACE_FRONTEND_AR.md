# معمارية الواجهة والأسواق المتعددة

**النطاق:** `apps/web` فقط.  
**آخر مراجعة:** 2026-08-16.

## 1. حدود النظام

```text
[زائر أو حساب Marketplace]
             │
             ▼
[React Marketplace UI]
             │ marketplace key
             ▼
[Sky365 Marketplace API]
             │
             ▼
[Marketplace data in Sky365]
```

واجهة المستخدم لا تمنح صلاحية Admin ولا تفسر أدوار Sky365 الداخلية. نصوص الواجهة تفرق صراحة بين **Marketplace Account** وحساب منصة Sky365.

| المجال | المالك | الحالة |
| --- | --- | --- |
| العرض والتصفح والثيم وRTL | هذا المستودع / `apps/web` | VERIFIED |
| حسابات الزوار والتجار في السوق | Marketplace API | PARTIAL في الواجهة |
| ASP.NET Identity وWMS وTenant middleware | Sky365 Backend | خارج النطاق |
| SQL وSeed وSchema | Sky365 Backend | خارج النطاق |

## 2. اختيار السوق

المفتاح يقرأ من `?marketplace=<key>`، ثم من host mapping، ثم من القيمة الافتراضية. كل رابط داخلي يجب أن يستبقي المفتاح عن طريق `marketplaceHref` أو `marketplaceHrefForKey`.

أمثلة:

```text
/home?marketplace=mawashi-kuwait
/home?marketplace=magic-kuwait
/market?marketplace=cars-kuwait
/modules/auctions?marketplace=used-cars-heavy-transport
```

## 3. ثيمات وهوية السوق

`apps/web/src/lib/marketplaceTheme.js` يحتوي سجل الثيمات. الثيم يحدد اللون الأساسي والخلفية والـgradient لبطاقات اختيار السوق، ولا يغير نموذج البيانات أو الصلاحيات.

الأسواق التي لها تعريفات Theme حالية تشمل: المواشي، ماجيك الكويت، الخردة، السيارات، السيارات المستعملة والنقل الثقيل، العطور، ومستحضرات التجميل.

## 4. التنقل والموديولات

الـShell الموحد يقدم:

- الرئيسية والسوق كمسارات أساسية ثابتة.
- Mega menu للموديولات التي يعيدها `GET /marketplaces/{key}/modules`.
- إظهار الموديول فقط إذا كان مفعلًا من الـAPI.
- تبديل السوق، حالة الحساب، رابط Sky365 العام، ورقم إصدار الواجهة في الشريط العلوي.

إضافة أو نقل موديول بين الأسواق قرار Backend/Data؛ الواجهة تتلقى النتيجة ولا تخترع موديولات أو صلاحيات محلية.

## 5. حالات الواجهة

| الحالة | المعالجة |
| --- | --- |
| Loading | نص أو Skeleton حسب الشاشة |
| API unavailable / 5xx | Maintenance Gate |
| 401/403 | حالة دخول أو Access Denied دون ادعاء صلاحيات إضافية |
| لا توجد بيانات | Empty state واضح |
| هاتف أو شاشة صغيرة | قائمة Mobile بديلة عن التنقل المكتبي |

## 6. مؤشرات الإصدار والنشر

`VITE_MARKETPLACE_RELEASE` يعرض قيمة إصدار عامة في الـShell. لا يحتوي على سر. يجب أن تضبطه CI/CD عند وجود سياسة إصدار رسمية؛ القيمة الحالية الافتراضية هي `v1.0.0-beta.1`.

النشر الجاري: GitHub Actions إلى Azure Static Web Apps. إثبات نجاح build/deploy لا يساوي UAT كامل للـAPI أو للعمليات التجارية.
