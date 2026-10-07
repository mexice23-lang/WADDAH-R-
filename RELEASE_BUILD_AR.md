# تجهيز WADDAH R للإصدار

## قبل بناء Release
1. أنشئ Firebase Project حقيقي.
2. فعّل Authentication وFirestore وStorage وFCM.
3. نزّل `google-services.json` وضعه في `app/`. لا ترفع الملف إلى مستودع عام إذا كان إعداد المشروع يحتوي معلومات خاصة.
4. انشر `firestore.rules` و`storage.rules` بعد مراجعتها.
5. أنشئ Admin Custom Claim باسم `admin=true` للحساب الإداري فقط.
6. أنشئ مفتاح توقيع Android محفوظًا خارج المشروع.

## البناء
- من Android Studio: Build > Generate Signed Bundle / APK > Android App Bundle.
- اختر `release` ثم keystore الخاص بك.
- الناتج يكون AAB مناسبًا للرفع إلى Google Play.

## مهم
هذا المشروع لا يحتوي على keystore أو `google-services.json` الحقيقي؛ هذه عناصر خاصة بحسابك ولا يجب تضمينها في ملف المشروع العام.

قبل النشر النهائي اختبر تسجيل الحساب، رفع الصور، المنشورات، التعليقات، الرسائل، الإشعارات، الحظر، البلاغات وحذف الحساب على جهاز حقيقي.
