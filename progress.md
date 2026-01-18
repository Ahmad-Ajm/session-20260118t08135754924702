# Features Map – Project Feature Inventory

هذا الملف هو الخريطة المركزية لجميع الميزات (Features / Epics) في المشروع.
الهدف منه:

- إعطاء صورة واضحة عن **كل ميزة**: ماذا تفعل؟ لمن؟ وأين توجد مواصفاتها؟
- ربط كل ميزة بنوعها **FeatureType** لاختيار قالب الـ KPI والـ Prompt المناسب.
- أن يكون نقطة البداية لأي عمل جديد على الميزات (Spec Kit, Feature Factory, Testing).

## Feature Types & KPI Templates

لكل ميزة يتم تحديدها في جدول الـ Features يجب تعيين قيمة **FeatureType** بدقة.  
ويتم استخدام **قوالب KPI Templates المتخصصة** لضمان جودة ثابتة لكل نوع من الميزات.

---

## 1. أنواع الميزات (FeatureType)

استخدم أحد القيم التالية في عمود `FeatureType`:

- `CRUD`          – ميزات إنشاء/عرض/تعديل/حذف لكيان معيّن (Full Stack).
- `Reporting`     – تقارير ولوحات تحكم وتحليلات.
- `Search`        – بحث وفلاتر وترتيب ونتائج.
- `Workflow`      – حالات وموافقات وتدفقات عمل.
- `Notifications` – إشعارات Email / SMS / Push / In-App.
- `Integration`   – تكامل مع أنظمة أو APIs خارجية.
- `AI`            – ميزات ذكاء صناعي (Chat, RAG, Agents, Recommendations...).
- `Security`      – صلاحيات، أدوار، سياسات أمان، Auth / AuthZ.

يمكن إضافة أنواع أخرى لاحقًا 

### العلاقة الإلزامية بين FeatureType وقالب الـ KPI:

- عند تحديد `FeatureType = CRUD`  
  يجب استخدام قالب الـ KPI التالي كـ **Definition of Done** للميزة:  
  `specifications/12-testing/kpi-crud-template.md`

- عند تحديد `FeatureType = Reporting`  
  يجب استخدام قالب الـ KPI التالي:  
  `specifications/12-testing/kpi-reporting-template.md`

- عند تحديد `FeatureType = Search`  
  يجب استخدام قالب الـ KPI التالي:  
  `specifications/12-testing/kpi-search-template.md`

- عند تحديد `FeatureType = Workflow`  
  يجب استخدام قالب الـ KPI التالي:  
  `specifications/12-testing/kpi-workflow-template.md`

- عند تحديد `FeatureType = Notifications`  
  يجب استخدام قالب الـ KPI التالي:  
  `specifications/12-testing/kpi-notifications-template.md`

- عند تحديد `FeatureType = Integration`  
  يجب استخدام قالب الـ KPI التالي:  
  `specifications/12-testing/kpi-integration-template.md`

- عند تحديد `FeatureType = AI`  
  يجب استخدام قالب الـ KPI التالي:  
  `specifications/12-testing/kpi-ai-template.md`

- عند تحديد `FeatureType = Security`  
  يجب استخدام قالب الـ KPI التالي:  
  `specifications/12-testing/kpi-security-template.md`
---

## 2. نظرة عامة – جدول الميزات

املأ هذا الجدول لكل Feature رئيسية في المشروع.

- **FeatureId**: معرف قصير ثابت (FEAT-XXXX).
- **FeatureName**: اسم الميزة بشكل مفهوم للبشر.
- **FeatureType**: أحد الأنواع المذكورة أعلاه.
- **Summary**: ملخّص قصير (سطر واحد) لوظيفة الميزة.
- **Personas**: من سيستخدم هذه الميزة؟ (User, Admin, Owner, Broker, ...).
- **Requirements**: معرفات المتطلبات المرتبطة (FR-01, NFR-02, ... إن وُجدت).
- **SpecFolders**: المجلدات/الملفات في `specifications/*` التي تتعلق بهذه الميزة.
- **Priority**: أولوية التنفيذ (P0, P1, P2, ...).
- **Status**: حالة الميزة (Planned, In-Progress, Done, Deprecated, ...).

> 👇 النموذج التالي يحتوي صفًا واحدًا **مثالًا فقط**.
> عدّل القيم أو انسخ الصف وأضف صفوفًا جديدة لكل ميزة.

| FeatureId      | FeatureName        | FeatureType | Summary                                      | Personas         | Requirements      | SpecFolders                             | Priority | Status      |
|----------------|--------------------|-------------|----------------------------------------------|------------------|-------------------|------------------------------------------|----------|------------|
| FEAT-EXAMPLE01 | Example Feature    | CRUD        | مثال لميزة CRUD كاملة (إنشاء/عرض/تعديل/حذف) | Admin, User      | FR-EX-01, FR-EX-02 | 04-domain, 07-api, 08-ui                | P1       | Planned    |
| FEAT-CV-CREATION | CV Creation | CRUD | إنشاء/تعديل/عرض السيرة الذاتية من بيانات المستخدم وتخزينها لعرضها لاحقاً | User, Visitor | FR-001, FR-003, FR-004, FR-005 | psec-kit-file/FEAT-CV-CREATION | P0 | Planned |
| FEAT-USER-REGISTRATION | User Registration | Security | تسجيل المستخدمين وتسجيل الدخول لحماية ميزات إنشاء/تعديل السيرة الذاتية | User |  | psec-kit-file/FEAT-USER-REGISTRATION | P0 | Planned |

أضف الصفوف الحقيقية هنا أسفل المثال ↑.

---

## 3. تفاصيل الميزات (Feature Details)

اكتب سكشن منفصل لكل Feature، بنفس القالب التالي.
يمكنك نسخ الـ Template ولصقه لكل ميزة ثم تعبئته.

> لا تحذف هذا القالب؛ فقط انسخه أسفله لكل ميزة.

### Template – انسخ هذا البلوك لكل ميزة جديدة

```md
### <FeatureId> – <FeatureName>
**Type:** <FeatureType>  
**Summary:** وصف مختصر للميزة في سطر أو سطرين يوضح الهدف التجاري.  
**Personas:** اذكر المستخدمين أو الأدوار المستهدفة (مثال: Admin, Owner, Buyer).  
**Requirements:** FR-xx, NFR-xx (إن وُجدت) أو اتركها فارغة مؤقتًا.  
**Spec Folders / Files:**  
- `specifications/XX-something/...`
- `specifications/YY-other/...`

**Dependencies / Relations:**  
- تعتمد على: (مثال: FEAT-AUTH, FEAT-SEARCH)  
- تؤثر على: (مثال: FEAT-REPORTS)

**KPI Template:**  
- إذا كان النوع `CRUD` → استخدم: `specifications/12-testing/kpi-crud-template.md`  
- إذا كان `Reporting` → استخدم: `specifications/12-testing/kpi-reporting-template.md`  
- إذا كان `Search` → استخدم: `specifications/12-testing/kpi-search-template.md`  
- إذا كان `Workflow` → استخدم: `specifications/12-testing/kpi-workflow-template.md`  
- إذا كان `Notifications` → استخدم: `specifications/12-testing/kpi-notifications-template.md`  
- إذا كان `Integration` → استخدم: `specifications/12-testing/kpi-integration-template.md`  
- إذا كان `AI` → استخدم: `specifications/12-testing/kpi-ai-template.md`  
- إذا كان `Security` → استخدم: `specifications/12-testing/kpi-security-template.md`

**Recommended Feature Prompt (Cursor):**  
- `cursor_prompt_feature-<type>.txt`

**Notes / Open Questions:**  
- ضع هنا أي أسئلة أو نقاط غير محسومة بعد.
```

---

## 4. مثال عملي مكتمل لميزة واحدة (يمكنك حذفه أو تعديله)

المثال التالي فقط لتوضيح كيفية تعبئة التفاصيل. غيّره بما يناسب مشروعك.

### FEAT-CITIES – City Management
**Type:** CRUD  
**Summary:** إدارة المدن (إضافة مدينة جديدة، تعديل بيانات مدينة، حذف/تعطيل مدينة، عرض قائمة المدن مع البحث والفلاتر البسيطة).  
**Personas:** Admin  
**Requirements:** FR-10, FR-11 (أمثلة؛ غيّرها بما يناسبك)  
**Spec Folders / Files:**  
- `specifications/04-domain/locations.md`  
- `specifications/07-api/cities-api.md`  
- `specifications/08-ui/cities-screens.md`  

**Dependencies / Relations:**  
- تعتمد على: FEAT-AUTH (لمنع الوصول لغير المديرين)  
- تؤثر على: FEAT-REPORTS (تقارير تعتمد على المدن)، FEAT-SEARCH (بحث حسب المدينة)  

**KPI Template:**  
- `specifications/12-testing/kpi-crud-template.md`

**Recommended Feature Prompt (Cursor):**  
- `cursor_prompt_feature-crud.txt`

**Notes / Open Questions:**  
- هل نحتاج حقل كود المدينة (Code) موحّد مع نظام خارجي؟  
- هل نسمح بالتعطيل بدل الحذف النهائي؟

---

بعد هذا المثال، ابدأ بإضافة سكاشن حقيقية لكل Feature في مشروعك بنفس القالب.
يمكنك ترتيبها حسب الأولوية أو حسب الدومين (Auth, Users, Search, Reporting, AI, Integration, ...).

### FEAT-CV-CREATION – CV Creation
**Type:** CRUD  
**Summary:** تمكين المستخدم من إدخال بياناته (الاسم، الموبايل، الصورة، الخبرات، التعليم) وإنشاء/عرض/تعديل السيرة الذاتية وتخزينها لعرضها والبحث عنها.  
**Personas:** User, Visitor  
**Requirements:** FR-001, FR-003, FR-004, FR-005, NFR-001  
**Spec Folders / Files:**  
- `psec-kit-file/FEAT-CV-CREATION/clarify.md`
- `psec-kit-file/FEAT-CV-CREATION/plan.md`
- `psec-kit-file/FEAT-CV-CREATION/specify.md`
- `psec-kit-file/FEAT-CV-CREATION/tasks.md`

**Dependencies / Relations:**  
- تعتمد على: FEAT-USER-REGISTRATION (لإنشاء/تعديل CV كمستخدم مسجّل)  
- تؤثر على: (لاحقاً) FEAT-SEARCH (إذا تم فصل البحث كميزة مستقلة)

**KPI Template:**  
- `specifications/12-testing/kpi-crud-template.md`

**Recommended Feature Prompt (Cursor):**  
- `cursor_prompt_feature-crud.txt`

**Notes / Open Questions:**  
- ما تعريف "السير الذاتية المتاحة" للزوار؟ وهل يوجد زر نشر/إلغاء نشر؟
- ما هي "البيانات الحساسة" التي يجب إخفاؤها عند التصدير (هل رقم الموبايل ضمنها)؟
- صيغة التصدير المطلوبة (PDF/طباعة/رابط) غير محددة.

### FEAT-USER-REGISTRATION – User Registration
**Type:** Security  
**Summary:** تسجيل المستخدمين وتسجيل الدخول/الخروج وحماية عمليات إنشاء/تعديل السيرة الذاتية.  
**Personas:** User  
**Requirements:**  
**Spec Folders / Files:**  
- `psec-kit-file/FEAT-USER-REGISTRATION/clarify.md`
- `psec-kit-file/FEAT-USER-REGISTRATION/plan.md`
- `psec-kit-file/FEAT-USER-REGISTRATION/specify.md`
- `psec-kit-file/FEAT-USER-REGISTRATION/tasks.md`

**Dependencies / Relations:**  
- تؤثر على: FEAT-CV-CREATION (التحكم في الوصول والتعديل)  

**KPI Template:**  
- `specifications/12-testing/kpi-security-template.md`

**Recommended Feature Prompt (Cursor):**  
- `cursor_prompt_feature-security.txt`

**Notes / Open Questions:**  
- حقول وآلية التسجيل (بريد/هاتف/كلمة مرور/OTP) غير محددة في ملخص المتطلبات.
- هل نحتاج أدوار/صلاحيات إضافية (Admin)؟
