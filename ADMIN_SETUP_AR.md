# إعداد مدير WADDAH R

لوحة الإدارة محمية الآن بواسطة Firebase Authentication Custom Claim باسم `admin`.

## الطريقة الموصى بها
استخدم Firebase Admin SDK من جهاز إداري/بيئة خادم موثوقة فقط.
لا تضع ملف Service Account داخل تطبيق Android.

مثال Node.js بعد إعداد Firebase Admin SDK:

```js
const admin = require('firebase-admin');
admin.initializeApp();

admin.auth().setCustomUserClaims('USER_UID_HERE', { admin: true })
  .then(() => console.log('Admin claim set'));
```

استبدل `USER_UID_HERE` بـ UID حساب المدير الحقيقي.

بعد ذلك سجّل خروج المدير ودخوله مرة أخرى، أو نفّذ Force Token Refresh، لكي يحصل على claim الجديد.

قواعد Firestore وStorage تتحقق من `request.auth.token.admin == true`؛ لذلك لا يكفي تغيير الواجهة أو تعديل APK للحصول على صلاحيات المدير.
