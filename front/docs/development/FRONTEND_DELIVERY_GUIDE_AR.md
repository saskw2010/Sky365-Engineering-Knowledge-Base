# دليل تطوير وتسليم واجهة Mawashigate

## بيئة محلية

```bash
npm ci
npm run dev --prefix apps/web
npm run build --prefix apps/web
npm run lint --prefix apps/web
```

خادم التطوير الافتراضي هو `http://localhost:3000`، ويخرج البناء إلى `dist/apps/web`.

## متغيرات الواجهة العامة

ابدأ من `apps/web/.env.example`.

| المتغير | الاستخدام | قاعدة أمان |
| --- | --- | --- |
| `VITE_MARKETPLACE_API_URL` | عنوان Marketplace API | عنوان عام فقط؛ لا connection string |
| `VITE_MARKETPLACE_KEY` | السوق الافتراضي | لا يبدل سياق الرابط الصريح |
| `VITE_SKY365_BACKEND_PORTAL_URL` | رابط Sky365 العام في الـShell | ليس رابط إدارة حساسًا |
| `VITE_MARKETPLACE_RELEASE` | رقم إصدار ظاهر للمستخدم | لا يحمل أسرارًا |
| `VITE_MARKETPLACE_PROXY_TARGET` | Proxy محلي فقط | لا ينشر للإنتاج |

أي متغير يبدأ بـ`VITE_` يضمّن في المتصفح؛ لا تستخدمه لكلمات المرور أو Tokens أو مفاتيح الدفع.

## Pipeline النشر

الملف: `.github/workflows/azure-static-web-apps-mango-plant-0ee956010.yml`.

1. `pull_request` إلى `main`: Build + بيئة مراجعة Azure Static Web Apps.
2. `push` إلى `main`: Build + نشر الإنتاج.
3. Azure يعتمد على `AZURE_STATIC_WEB_APPS_API_TOKEN` المحفوظ في GitHub Secrets.

لا تدوّر المفتاح ولا تغيّر مورد Azure من Pull Request واجهة دون اعتماد DevOps.

## قائمة تحقق قبل Pull Request

- [ ] احتفظت بسياق `marketplace` في الروابط.
- [ ] لم تخلط Marketplace Account مع Sky365 Admin.
- [ ] أضفت حالات loading/error/empty/access denied حيث يلزم.
- [ ] راجعت RTL والموبايل ولوحة المفاتيح.
- [ ] شغلت build وlint.
- [ ] لم تضف Secret أو بيانات شخصية حقيقية أو تغيّر API contract.

## طلب تغيير Backend

إذا احتاج UI endpoint أو حقلًا جديدًا، لا تنفذ Backend/SQL من هنا. ارفع طلبًا بهذه الحقول:

```text
RequestId:
المطلوب بدقة:
API أو الملف المتأثر:
السبب:
الحالة: VERIFIED / PARTIAL / UNRESOLVED
أثر عدم التنفيذ:
```
