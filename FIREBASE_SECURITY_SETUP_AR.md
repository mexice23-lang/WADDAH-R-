# WADDAH R — إعداد Firebase والأمان

هذه النسخة تستخدم قواعد مقيّدة بدل السماح العام بالقراءة والكتابة.

## 1) إنشاء مشروع Firebase
1. افتح Firebase Console.
2. أنشئ مشروعًا جديدًا باسم WADDAH R.
3. أضف تطبيق Android بالحزمة `com.nova.social`.
4. نزّل `google-services.json` وضعه داخل مجلد `app/`.

## 2) Authentication
فعّل:
- Email/Password

لا تضع أي Server Key أو Service Account داخل تطبيق Android.

## 3) Firestore
أنشئ Cloud Firestore Database.
ثم انشر الملف `firestore.rules` من Firebase Console > Firestore > Rules، أو باستخدام Firebase CLI:

`firebase deploy --only firestore`

## 4) Storage
فعّل Cloud Storage.
ثم انشر `storage.rules`:

`firebase deploy --only storage`

قواعد Storage تسمح للمستخدم بإدارة صور مساره فقط، وتتحقق من نوع الملف والحجم.

## 5) صلاحية المشرف
لوحة الإدارة لا تعتمد على بريد ثابت.
يجب منح حساب المشرف Firebase Auth Custom Claim باسم:

`admin: true`

بعد تغيير الـ claim، يجب تحديث ID token للمستخدم (إعادة تسجيل الدخول أو Force Refresh) حتى تظهر الصلاحية في التطبيق.

## 6) App Check
قبل النشر العام، فعّل Firebase App Check لتطبيق Android باستخدام Play Integrity بعد إعداد التطبيق في Firebase Console.

## 7) لا تستخدم قواعد مفتوحة
لا تستخدم `allow read, write: if true` في الإنتاج.
قواعد Firebase تُطبّق خارج التطبيق وهي خط الدفاع الأساسي حتى لو تم تعديل APK.

## 8) اختبار
استخدم Rules Simulator في Firebase Console، ويفضل اختبار القواعد أيضًا عبر Firebase Emulator قبل النشر.
