# 📱 نظام الحضور والانصراف
## تطبيق Flutter - Android & iOS

---

## 🚀 خطوات تشغيل المشروع

### 1. تثبيت Flutter
```bash
# تحميل Flutter SDK من:
https://flutter.dev/docs/get-started/install

# التحقق من التثبيت:
flutter doctor
```

### 2. تثبيت Dependencies
```bash
cd attendance_app
flutter pub get
```

### 3. تشغيل التطبيق
```bash
# على محاكي Android أو iOS:
flutter run

# بناء APK للأندرويد:
flutter build apk --release

# بناء للـ iOS:
flutter build ios --release
```

---

## 🗂️ هيكل الملفات
```
lib/
├── main.dart                    # نقطة البداية
├── theme.dart                   # ألوان وتصميم
├── models/
│   ├── employee.dart            # نموذج الموظف
│   └── attendance_record.dart   # نموذج سجل الحضور
├── services/
│   ├── storage_service.dart     # حفظ البيانات محلياً
│   └── location_service.dart   # خدمة GPS
└── screens/
    ├── login_screen.dart        # شاشة الدخول (PIN)
    ├── employee_home_screen.dart # شاشة الموظف
    ├── employee_history_screen.dart # سجل الموظف
    ├── admin_screen.dart        # لوحة المدير
    └── add_employee_screen.dart # إضافة موظف
```

---

## 🔑 بيانات الدخول الافتراضية

| المستخدم | الرقم السري |
|----------|------------|
| المدير   | **0000**   |

> غيّر الرقم السري للمدير فوراً بعد أول دخول!

---

## ✨ المميزات

### للموظف:
- ✅ تسجيل الحضور بالموقع الجغرافي (GPS)
- ✅ تسجيل الانصراف بالموقع الجغرافي
- ✅ ساعة مباشرة
- ✅ عرض حالة اليوم (حاضر / متأخر / انصرف)
- ✅ سجل الحضور الشهري

### للمدير:
- ✅ لوحة تحكم شاملة
- ✅ عرض حضور اليوم لجميع الموظفين
- ✅ إضافة وحذف الموظفين
- ✅ عرض سجل كل موظف
- ✅ إحصائيات (حاضر / غائب / متأخر)
- ✅ إعدادات اسم الشركة

---

## ⚙️ Dependencies المستخدمة

```yaml
geolocator: ^11.0.0        # GPS والموقع الجغرافي
shared_preferences: ^2.2.2 # حفظ البيانات محلياً
google_fonts: ^6.1.0       # خط Cairo العربي
flutter_animate: ^4.3.0    # الحركات والانيميشن
intl: ^0.19.0              # التواريخ بالعربي
uuid: ^4.3.3               # توليد IDs
```

---

## 📋 الأذونات المطلوبة

### Android (AndroidManifest.xml):
```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
```

### iOS (Info.plist):
```
NSLocationWhenInUseUsageDescription
NSLocationAlwaysAndWhenInUseUsageDescription
```

---

## 🔮 تطوير مستقبلي (ممكن إضافته)
- [ ] تصدير تقارير Excel/PDF
- [ ] إشعارات التأخير
- [ ] صورة الموظف
- [ ] تحديد نطاق جغرافي محدد للعمل (Geofencing)
- [ ] مزامنة مع السيرفر (Firebase)
- [ ] QR Code للحضور

---

## 🛠️ استكشاف الأخطاء

**مشكلة GPS:** تأكد أن الجهاز فعّل خدمة الموقع  
**مشكلة البناء:** شغّل `flutter clean && flutter pub get`  
**iOS لا يعمل:** تأكد من Xcode وصلاحيات الموقع في Info.plist
