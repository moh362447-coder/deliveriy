# 🔧 دليل الإعداد السريع

## الخطوة 1: إنشاء ملف .env

قم بنسخ محتوى `.env.example` إلى ملف جديد باسم `.env`:

```bash
cp .env.example .env
```

## الخطوة 2: تحديث إعدادات قاعدة البيانات

افتح ملف `.env` وحدّث الإعدادات التالية:

```env
DATABASE_URL=postgresql://YOUR_USERNAME:YOUR_PASSWORD@localhost:5432/dilevery_db
```

## الخطوة 3: إعداد Gmail للبريد الإلكتروني

1. انتقل إلى https://myaccount.google.com/security
2. فعّل "التحقق بخطوتين" (2-Step Verification)
3. انتقل إلى "كلمات مرور التطبيقات" (App Passwords)
4. أنشئ كلمة مرور جديدة للتطبيق
5. انسخ كلمة المرور واستخدمها في `.env`:

```env
EMAIL_USER=your-email@gmail.com
EMAIL_PASSWORD=xxxx xxxx xxxx xxxx
```

## الخطوة 4: إنشاء قاعدة البيانات

```bash
# إنشاء قاعدة بيانات PostgreSQL
createdb dilevery_db

# أو باستخدام psql
psql -U postgres
CREATE DATABASE dilevery_db;
\q
```

## الخطوة 5: تشغيل Migrations

```bash
npm run db:push
```

## الخطوة 6: تشغيل التطبيق

افتح نافذتي terminal:

**Terminal 1 - Backend:**
```bash
npm run server
```

**Terminal 2 - Frontend:**
```bash
npm run dev
```

## 🎉 جاهز!

افتح المتصفح على: http://localhost:5173

---

## 🔍 استكشاف الأخطاء

### خطأ في الاتصال بقاعدة البيانات
- تأكد من تشغيل PostgreSQL
- تحقق من صحة `DATABASE_URL` في `.env`

### خطأ في إرسال البريد الإلكتروني
- تأكد من تفعيل "التحقق بخطوتين" في Gmail
- استخدم كلمة مرور التطبيق وليس كلمة مرور حسابك

### خطأ في تحميل الخريطة
- تحقق من اتصالك بالإنترنت
- الخريطة تستخدم OpenStreetMap (مجاني)
