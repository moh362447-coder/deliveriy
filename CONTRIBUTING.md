# 🤝 المساهمة في Dilevery Pro

نرحب بمساهماتكم! هذا الدليل سيساعدك على البدء.

## 📋 قواعد المساهمة

### 1. معايير الكود

#### TypeScript
- استخدم TypeScript في جميع الملفات
- تجنب استخدام `any` قدر الإمكان
- استخدم interfaces و types بشكل صحيح

#### React
- استخدم Functional Components مع Hooks
- تجنب استخدام Class Components
- استخدم `memo` للمكونات التي تُعاد رسمها كثيراً

#### CSS/Tailwind
- استخدم Tailwind CSS للتصميم
- تجنب inline styles
- استخدم CSS variables للألوان

#### Clean Code
```typescript
// ✅ جيد
function calculateDeliveryFee(distance: number): number {
  const baseFee = 300;
  const perKmFee = 50;
  return distance <= 5 ? baseFee : baseFee + (distance - 5) * perKmFee;
}

// ❌ سيء
function calc(d: any) {
  return d <= 5 ? 300 : 300 + (d - 5) * 50;
}
```

### 2. Git Workflow

#### Branches
- `main` - الإنتاج (Production)
- `develop` - التطوير (Development)
- `feature/feature-name` - ميزة جديدة
- `fix/bug-name` - إصلاح خطأ
- `docs/update-name` - تحديث الوثائق

#### Commit Messages
استخدم الصيغة التالية:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: ميزة جديدة
- `fix`: إصلاح خطأ
- `docs`: تحديث الوثائق
- `style`: تنسيق الكود
- `refactor`: إعادة هيكلة الكود
- `test`: إضافة اختبارات
- `chore`: مهام صيانة

**أمثلة:**
```bash
feat(auth): add email verification system
fix(map): correct Algeria default coordinates
docs(readme): update installation guide
```

### 3. Pull Request Process

1. Fork المشروع
2. أنشئ branch جديد:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. قم بالتغييرات المطلوبة
4. Commit التغييرات:
   ```bash
   git commit -m 'feat: add amazing feature'
   ```
5. Push إلى branch:
   ```bash
   git push origin feature/amazing-feature
   ```
6. افتح Pull Request

### 4. Code Review

سيتم مراجعة جميع Pull Requests قبل الدمج. تأكد من:

- ✅ الكود يعمل بدون أخطاء
- ✅ لا توجد console.log غير ضرورية
- ✅ الكود منسق بشكل صحيح
- ✅ التعليقات واضحة (إن وُجدت)
- ✅ لا توجد ملفات غير ضرورية

### 5. Testing (قريباً)

سيتم إضافة اختبارات قريباً. في الوقت الحالي، تأكد من:

- اختبار الميزة يدوياً
- التحقق من جميع الحالات الممكنة
- اختبار على متصفحات مختلفة

## 🐛 الإبلاغ عن الأخطاء

عند الإبلاغ عن خطأ، يرجى تضمين:

1. **وصف الخطأ**: ما هو الخطأ بالضبط؟
2. **خطوات إعادة الإنتاج**: كيف يمكن إعادة إنتاج الخطأ؟
3. **السلوك المتوقع**: ما الذي كان يجب أن يحدث؟
4. **لقطات الشاشة**: إن أمكن
5. **البيئة**: نظام التشغيل، المتصفح، إلخ

## 💡 اقتراح ميزات جديدة

نرحب بالأفكار الجديدة! عند اقتراح ميزة:

1. **الوصف**: ما هي الميزة المقترحة؟
2. **الفائدة**: لماذا هذه الميزة مفيدة؟
3. **التنفيذ**: كيف يمكن تنفيذها؟ (اختياري)

## 📝 تحديث الوثائق

إذا أضفت ميزة جديدة، يرجى تحديث:

- README.md
- API_DOCS.md (إذا كانت API)
- التعليقات في الكود

## 🌍 الترجمة

نرحب بإضافة لغات جديدة! لإضافة لغة:

1. افتح `client/src/i18n/config.ts`
2. أضف الترجمات الجديدة
3. حدّث قائمة اللغات في `LanguageToggle.tsx`

## 🎨 التصميم

عند إضافة مكونات UI جديدة:

- استخدم نظام الألوان الموجود
- تأكد من دعم الوضع الليلي
- تأكد من دعم RTL للعربية
- استخدم Framer Motion للرسوم المتحركة

## 🔒 الأمان

إذا وجدت ثغرة أمنية، **لا تفتح issue عام**. بدلاً من ذلك:

1. أرسل بريد إلكتروني إلى: security@dilevery.com
2. صف الثغرة بالتفصيل
3. انتظر الرد قبل الكشف العام

## 📞 التواصل

- GitHub Issues: للأخطاء والميزات
- Discussions: للأسئلة والنقاشات
- Email: contact@dilevery.com

---

**شكراً لمساهمتك في جعل Dilevery Pro أفضل! 🚀**
