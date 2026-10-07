# إعداد WADDAH R v2 مع Firebase

هذه النسخة أصبحت مرتبطة بـ Firebase لتسجيل الحسابات والمنشورات ورفع الصور.

## 1) إنشاء مشروع Firebase
ادخل إلى Firebase Console وأنشئ مشروعاً جديداً.

## 2) إضافة تطبيق Android
استخدم اسم الحزمة:
com.nova.social

نزّل ملف:
google-services.json

ثم ضعه داخل:
app/google-services.json

يوجد ملف `google-services.json.example` كمثال فقط؛ لا تستخدمه للتشغيل.

## 3) تفعيل تسجيل الدخول
من Firebase Authentication:
- Sign-in providers
- فعّل Email/Password

## 4) إنشاء Firestore
أنشئ Cloud Firestore Database.

أنشئ Collection باسم:
posts

## 5) إنشاء Storage
فعّل Firebase Storage حتى يستطيع التطبيق رفع الصور.

## 6) التشغيل
افتح المشروع في Android Studio ثم:
Gradle Sync
ثم Run.

ملاحظة:
لا تضع بيانات سرية أو مفاتيح خاصة داخل التطبيق. ملف google-services.json يحتوي معرّفات مشروع Firebase وليس بديلاً عن قواعد الأمان. اضبط Firestore/Storage Security Rules قبل نشر التطبيق للعامة.

المرحلة الثانية تشمل:
- حسابات حقيقية
- تسجيل دخول وإنشاء حساب
- منشورات سحابية
- رفع صور
- إعجابات
- تسجيل خروج

المرحلة الثالثة يمكن أن تضيف:
- التعليقات
- المتابعة وإلغاء المتابعة
- الملف الشخصي والصورة الشخصية
- البحث
- الإشعارات
- المحادثات الخاصة
