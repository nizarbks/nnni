# 🌐 كيفاش تخلي الموقع ديالك يبقى دائم بالدومين - دليل كامل

الرابط الحالي `https://3000-....e2b.app` هو رابط مؤقت ديال التجربة وغادي يتمسح ملي تسالي الحصة. باش تخليه دائم وما يطيحش عمرك، خاصك دير هاد الخطوات (15 دقيقة).

## ✅ الحل الموصى به: Vercel + Neon + دومين خاص (الأرخص والأفضل)

### التكلفة السنوية:
- الدومين: 100-150 درهم / سنة (مثلا maison-douce.ma)
- الاستضافة: فابور 100% على Vercel Hobby (كافي لـ 10,000 زيارة / شهر)
- قاعدة البيانات: فابور على Neon.tech أو Supabase
- الإيميلات: فابور 3000 إيميل / شهر على Resend.com
- **المجموع: غير ثمن الدومين فقط!**

---

### الخطوة 1: شري دومين

اشري من واحد من هادو:
- **Namecheap.com** (أرخص وأسهل)
- **Hostinger.ma** (دعم عربي)
- **Gandi.net** أو **GoDaddy**

اقتراحات أسماء:
- maison-douce.ma
- ma-douce.com
- cozymoments.ma

### الخطوة 2: حساب GitHub (فابور)

1. سير لـ github.com ودير حساب
2. دير New Repository سميه `maison-douce`
3. فالترمينال ديال المشروع ديالك دير:

```bash
git init
git add .
git commit -m "Initial: 6 colors, address optional, domain ready"
git branch -M main
git remote add origin https://github.com/USERNAME/maison-douce.git
git push -u origin main
```

### الخطوة 3: قاعدة بيانات دائمة (بدل المحلية)

الساندبوكس الحالي كيتمسح، خاصك قاعدة بيانات سحابية دائمة:

**Option A - Neon.tech (موصى به - سهل):**
1. سير لـ neon.tech ودير حساب فابور
2. Create Project -> سميه `maison-douce`
3. غادي يعطيك رابط بحال: `postgresql://user:pass@ep-xxx.neon.tech/dbname`
4. نسخو - هذا هو DATABASE_URL الجديد

**Option B - Supabase:**
1. supabase.com -> New Project
2. Project Settings -> Database -> Connection String

### الخطوة 4: ديبلوي فـ Vercel (دائم وما كيطيحش)

1. سير لـ **vercel.com** ودير حساب بـ GitHub ديالك
2. Add New Project -> Import من GitHub -> اختار `maison-douce`
3. **قبل ما تدير Deploy**، زيد Environment Variables:

```
DATABASE_URL=postgresql://... من Neon
NEXT_PUBLIC_SITE_URL=https://maison-douce.ma (الدومين اللي شريتي)
ADMIN_PASSWORD=douce2026 (بدلها لحاجة صعيبة)
NEXT_PUBLIC_ADMIN_PASSWORD=douce2026
RESEND_API_KEY=re_xxx (من resend.com - اختياري ولكن مستحسن)
RESEND_FROM=Maison Douce <orders@maison-douce.ma>
```

4. كليك Deploy -> غادي يديبلوي فـ 2 دقائق ويعطيك رابط `maison-douce.vercel.app` (دائم)

### الخطوة 5: ربط الدومين

1. فـ Vercel -> مشروعك -> Settings -> Domains -> Add Domain
2. كتب الدومين ديالك: `maison-douce.ma` و `www.maison-douce.ma`
3. Vercel غادي يعطيك 2 سجلات DNS:

```
Type: A, Name: @, Value: 76.76.21.21
Type: CNAME, Name: www, Value: cname.vercel-dns.com
```

4. سير لـ Namecheap / Hostinger -> Domain -> Advanced DNS -> زيد هاد السجلات
5. تسنى 5-10 دقايق -> الدومين كيولي خدام مع SSL (https) أوتوماتيك

### الخطوة 6: إعداد الإيميل الاحترافي ( باش ما يمشيش سبام)

1. سير لـ **resend.com** ودير حساب فابور
2. Domains -> Add Domain -> كتب `maison-douce.ma`
3. Resend كيعطيك 3 سجلات TXT زيدها فـ DNS (بحال الخطوة 5)
4. كليك Verify -> منين يتفعل، سير لـ API Keys -> Create API Key -> نسخ المفتاح `re_...`
5. زيدو فـ Vercel Env Vars -> Redeploy

دابا أي طلب -> كيجيك من `orders@maison-douce.ma` -> لـ `nizarbks59@gmail.com` - احترافي 100%

---

## 🔒 كيفاش تخليه ما يطيحش أبدا؟

1. **جدد الدومين كل سنة:** Namecheap كيصيفط لك إيميل قبل شهر - جددو (100 DH)
2. **Vercel فابور ديما:** ما كيتمسحش إلا إلا مسحتي الحساب بيدك
3. **Neon فابور ديما:** 0.5GB تخزين كافي لـ 50,000 طلب
4. **دير باك أب:** كل شهر سير لـ /admin وديّر تصدير CSV وحفظو عندك

---

## ⚠️ الفرق بين الحالي والدائم

| الحالي (e2b.app) | الدائم (دومين خاص) |
|---|---|
| يتمسح بعد ساعات/أيام | يبقى للأبد |
| ما كيتيقش فيه Facebook بزاف | Facebook كيتيق فيه 100% |
| ما كينش SSL مزيان | SSL احترافي |
| قاعدة البيانات كتتمسح | محفوظة ديما |
| ما تقدرش تدير Pixel | تقدر تدير Pixel, Analytics... |

---

## 🆘 إلا بغيتي نوجد لك كلشي؟

إلا ما بغيتيش تدير هادشي بيدك، نقدر نوجد لك:
- ملف ZIP فيه الكود كامل واجد للديبلوي
- فيديو شرح قصير
- أو نكتب لك الأوامر كاملين اللي تديرهم

قوليا غير شنو سميت الدومين اللي بغيتي وغادي نوجد لك كلشي ب `NEXT_PUBLIC_SITE_URL` ديالو.

الرابط الحالي غادي يبقى خدام حتى تدير الدومين الدائم - منين تدير الدومين، غير بدل الرابط فإعلانات Facebook وصافي.
