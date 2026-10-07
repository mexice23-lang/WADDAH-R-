# WADDAH R — المرحلة الرابعة

تمت إضافة:
- 💬 محادثات خاصة عبر Firestore.
- 🔔 إشعارات داخل التطبيق للمتابعة والرسائل.
- 👥 متابعة + تسجيل المتابع في قاعدة البيانات.
- 👤 إحصاءات الملف الشخصي.
- 💬 تحسين التعليقات.
- 🔐 استمرار Firebase Authentication.

## قبل الاستخدام
ضع `google-services.json` داخل مجلد `app` كما في المرحلة الثانية.

## بنية Firebase المستخدمة
- users/{uid}
- users/{uid}/following/{targetUid}
- followers/{uid}/items/{followerUid}
- posts/{postId}
- posts/{postId}/comments/{commentId}
- conversations/{conversationId}/messages/{messageId}
- notifications/{uid}/items/{notificationId}

## ملاحظة مهمة
هذه نسخة تعليمية/MVP. قواعد Firestore يجب تشديدها قبل نشر التطبيق للعامة، خصوصاً صلاحيات الرسائل والإشعارات. لا تعتمد على قواعد مفتوحة في الإنتاج.

المرحلة التالية المقترحة:
- صور شخصية حقيقية ورفعها إلى Storage.
- شاشة محادثات أجمل مع قائمة المحادثات.
- حذف/تعديل المنشورات.
- حظر وإبلاغ المستخدمين.
- إشعارات Push فعلية عبر Firebase Cloud Messaging.
- لوحة إدارة للمشرف.
