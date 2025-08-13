
# 💄 Waad Lash by SASO — سيستم كاشير ومخزون (Streamlit + Google Sheets)

**جاهز للأونلاين** — افتح من الموبايل أو اللابتوب. يدير منتجاتك، عملاءك، الطلبات، الفواتير، التقارير، وحركات المخزون.
- أسعار **جملة/قطاعي**
- خصم وتوصيل
- خصم تلقائي من المخزون
- **فاتورة HTML** للطباعة (تطلع PDF من المتصفح)
- تنبيه قرب النفاد
- رفع شعار المتجر من الإعدادات

---

## المتطلبات
- Google Account
- Google Spreadsheet واحدة (الـ ID تم ضبطه هنا بالفعل)
- Service Account (JSON) + مشاركة الشيت مع إيميل الـ Service Account كـ Editor

---

## إعداد سريع (مرة واحدة)
1) **Service Account**:
   - Google Cloud → APIs & Services → Credentials → Create Service Account.
   - Add Key → JSON (نزّل الملف).
   - شارك الشيت مع إيميل الـ Service Account بصلاحية **Editor**.

2) **Secrets**:
   - محليًا: اعمل ملف `.streamlit/secrets.toml` وانسخ محتوى `secrets.example.toml` ثم الصق JSON بتاع الـ Service Account مكان التعليق.
   - على Streamlit Cloud: ادخل Settings → Secrets والصق نفس المحتوى.

3) **تشغيل محلي**:
   ```bash
   pip install -r requirements.txt
   streamlit run app.py
   ```

4) **نشر مجاني (Streamlit Community Cloud)**:
   - ارفع المشروع على GitHub.
   - Deploy من Streamlit Cloud → اختار الريبو → ضيف Secrets (نفس `secrets.toml`).
   - خد اللينك وافتحه على الموبايل.

---

## ملحوظة عن البيانات
- عند أول تشغيل، التابات (`Products`… إلخ) بتتعمل تلقائيًا لو مش موجودة.
- عايز تحمل بياناتك؟ افتح الشيت ولصّق CSVs الموجودة في مجلد `data/`:
  - `products_waadlash.csv`
  - `customers_waadlash.csv`

---

## نصائح
- استخدم قارئ باركود USB/BT لقراءة الـ SKU مباشرة.
- لو المخزون كبر جدًا لاحقًا، نقدر ننقل لـ Supabase بسهولة.
