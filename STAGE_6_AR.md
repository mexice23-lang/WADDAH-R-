# WADDAH R — المرحلة السادسة

## الجديد
- 🛡️ لوحة Admin داخل التطبيق.
- 🚩 عرض آخر البلاغات.
- 🗑️ حذف البلاغات من لوحة الإدارة.
- 🧹 حذف المنشورات المخالفة من لوحة الإدارة.
- 🔔 Firebase Cloud Messaging لاستقبال Push Notifications.
- 📱 خدمة Android لاستقبال إشعارات FCM.

## إعداد Admin
داخل MainActivity.kt ستجد:
admin@example.com

استبدله ببريد حساب المشرف الخاص بك.

**تنبيه أمني:** لا تعتمد على فحص البريد داخل التطبيق وحده كحماية حقيقية. يجب أن تكون صلاحيات Admin في Firestore/Cloud Functions مبنية على claims أو آلية خادم موثوقة.

## FCM
بعد إضافة google-services.json:
1. فعّل Firebase Cloud Messaging.
2. نفّذ Gradle Sync.
3. امنح التطبيق إذن الإشعارات على Android 13+ عند الحاجة.
4. للإرسال الجماعي/الآلي استخدم Cloud Functions أو خادم موثوق، ولا تضع Server Key داخل التطبيق.

## الخطوة التالية
المرحلة السابعة المقترحة:
- تصميم احترافي كامل.
- صفحة Explore/Trending.
- Stories.
- فيديوهات.
- نظام بحث متقدم.
- تحسين قواعد Firebase والإنتاج.
- Cloud Functions للإشعارات والإشراف.
- إعداد نسخة Release للنشر على Google Play.
