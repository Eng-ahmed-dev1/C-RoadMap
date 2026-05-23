# 🚀 C# Backend Developer — Complete Roadmap

> خارطة طريق شاملة لمطور Backend بـ C#، من الأساسيات حتى إتقان الـ Low-Level.  
> مقسّمة على **5 مراحل** تضم **17 موضوعاً** متسلسلاً بشكل منطقي.

---

## 📋 جدول المحتويات

- [نظرة عامة](#نظرة-عامة)
- [المرحلة 1 — الأساس الحقيقي](#المرحلة-1--الأساس-الحقيقي)
- [المرحلة 2 — فهم الـ Magic](#المرحلة-2--فهم-الـ-magic)
- [المرحلة 3 — Architecture & Systems](#المرحلة-3--architecture--systems)
- [المرحلة 4 — Runtime & Frameworks](#المرحلة-4--runtime--frameworks)
- [المرحلة 5 — Low-Level Mastery](#المرحلة-5--low-level-mastery)
- [خريطة التسلسل الكاملة](#خريطة-التسلسل-الكاملة)

---

## نظرة عامة

هذه الـ Roadmap مصممة لمطوّر C# يريد أن يصبح **Backend Developer** قوي وعميق الفهم. الهدف مش مجرد حفظ APIs أو frameworks، لكن فهم **كيف تشتغل الأشياء من الداخل** — وده اللي بيفرّق بين developer عادي ومن يُعتمد عليه في production systems حقيقية.

**المتطلبات المسبقة:** معرفة أساسية بـ C# (syntax, classes, collections).

---

## المرحلة 1 — الأساس الحقيقي

> هذه المرحلة هي الأساس الذي تُبنى عليه كل المراحل التالية. لا تتجاوزها.

---

### 01 — OOP & SOLID

**لماذا مهم؟**  
ده الأساس اللي كل حاجة تانية مبنية عليه. Clean Architecture وDI وASP.NET Core كلهم قايمين على interfaces وabstractions صح.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Encapsulation | إخفاء التفاصيل الداخلية وتعريض واجهة نظيفة |
| Inheritance | متى تستخدمه ومتى تتجنبه |
| Polymorphism | شكل واحد، سلوكيات كتير |
| Abstraction | التعامل مع الـ contract مش الـ implementation |
| Single Responsibility Principle | كل class مسؤولة عن حاجة واحدة بس |
| Open/Closed Principle | مفتوح للتوسعة، مغلق للتعديل |
| Liskov Substitution Principle | الـ subclass لازم تقدر تحل محل الـ base class |
| Interface Segregation Principle | interfaces صغيرة ومتخصصة أحسن من interface ضخمة |
| Dependency Inversion Principle | اعتمد على abstractions مش concrete classes |

---

### 02 — Delegates / Lambdas / Functional Thinking

**لماذا مهم؟**  
الـ functions في C# تعتبر objects. LINQ وAsync وMiddleware وEF Core كلهم مبنيين على delegates وlambdas.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| `delegate` keyword | تعريف الأنواع الأساسية |
| `Func<T>` | method بترجع قيمة |
| `Action<T>` | method من نوع void |
| `Predicate<T>` | للـ conditions (بترجع bool) |
| Lambda expressions `=>` | كتابة anonymous functions |
| Closures | إزاي بتـ capture variables من الـ scope الخارجي |
| Callbacks | إزاي بتبعت function كـ argument |
| Events & event handlers | نظام الـ pub/sub في C# |
| Multicast delegates | delegate بيستدعي أكتر من method |

---

### 03 — Generics Advanced

**لماذا مهم؟**  
مش بس `List<T>`. لازم تعرف تكتب كود generic حقيقي ومرن بـ constraints صح.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Generic constraints | `where T : class`, `where T : new()` |
| Covariance | `IEnumerable<out T>` — الـ type يقدر يكون أشمل |
| Contravariance | `IComparer<in T>` — الـ type يقدر يكون أضيق |
| Generic methods vs classes | الفرق في الاستخدام |
| Generic interfaces وabstract classes | بناء abstractions مرنة |
| Multiple constraints combined | دمج أكتر من constraint |
| Reflection مع Generics | قراءة وإنشاء generic types في runtime |

---

## المرحلة 2 — فهم الـ Magic

> في هذه المرحلة بتفهم إزاي الـ framework بيشتغل تحت الغطاء.

---

### 04 — LINQ Deep Dive

**لماذا مهم؟**  
تحت الغطاء الموضوع أعمق بكتير من `Where()` و`Select()`. فهم الـ internals بيتجنب لك performance issues خطيرة.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| `IEnumerable` vs `IQueryable` | الفرق الجوهري في التنفيذ |
| Deferred Execution | امتى بيتنفذ الـ query فعلياً؟ |
| Immediate Execution | ليه `ToList()` بيغير كل حاجة؟ |
| Projection & Aggregation | `Select`, `Sum`, `Average`, `GroupBy` |
| Joins | `Join`, `GroupJoin`, Left Join |
| LINQ Chains internals | إزاي الـ pipeline بتشتغل |
| LINQ to SQL translation | إزاي بيتحوّل لـ SQL |
| Custom LINQ operators | كتابة `extension methods` خاصة |

---

### 05 — Expression Trees

**لماذا مهم؟**  
`x => x.Age > 18` مش مجرد function، ممكن تتحول لـ tree structure. EF Core وORMs كلهم بيقروا الكود ده ويحولوه لـ SQL.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| `Expression<Func<T>>` vs `Func<T>` | الفرق بين الكود القابل للتحليل والتنفيذ |
| `BinaryExpression` / `MemberExpression` | أنواع العقد في الـ tree |
| `ParameterExpression` | تمثيل الـ parameters |
| بناء Expression يدوياً | إنشاء dynamic queries |
| `ExpressionVisitor` | تعديل الـ trees |
| `Compile()` وتشغيل Runtime | تحويل الـ tree لـ executable code |
| Dynamic WHERE clauses | بناء فلاتر ديناميكية |
| Query Providers | إزاي بيشتغلوا من الداخل |

---

### 06 — Reflection

**لماذا مهم؟**  
ORMs وDI containers وSerialization libraries كلهم بيستخدموا Reflection بشكل ضخم. فهمه بيفسرلك إزاي الـ frameworks بتشتغل.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| `Type.GetType()` & `typeof()` | الحصول على معلومات الـ type |
| `MethodInfo` / `PropertyInfo` / `FieldInfo` | فحص أعضاء الـ class |
| `Invoke()` ديناميكي | استدعاء methods في runtime |
| Custom Attributes | تعريف attributes خاصة وقراءتها |
| Assembly Loading | تحميل assemblies ديناميكياً |
| `Activator.CreateInstance()` | إنشاء objects بدون `new` |
| Performance Cost | إزاي تخفف التكلفة |
| Source Generators | البديل الحديث لـ Reflection |

---

## المرحلة 3 — Architecture & Systems

> هنا بتبني systems قابلة للتوسع والصيانة.

---

### 07 — Dependency Injection

**لماذا مهم؟**  
بعد ما فهمت interfaces وReflection، دلوقتي تقدر تفهم إزاي ASP.NET Core بيبني objects أوتوماتيك runtime.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Service Lifetimes | الفرق الجوهري بين الأنواع الثلاثة |
| Singleton | instance واحد طول عمر الـ app |
| Scoped | instance جديد لكل HTTP request |
| Transient | instance جديد كل مرة بتطلبه |
| Constructor Injection | الطريقة الأساسية |
| `IServiceCollection` Registration | تسجيل الـ services |
| Factory Pattern مع DI | إنشاء services ديناميكياً |
| Keyed Services (.NET 8+) | تسجيل أكتر من implementation لنفس الـ interface |

---

### 08 — Clean Architecture

**لماذا مهم؟**  
دلوقتي عندك الأدوات اللي تخليك تبني systems قابلة للتوسع والصيانة. مش spaghetti code.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Layers | Domain / Application / Infrastructure / Presentation |
| Separation of Concerns | كل layer مسؤولة عن حاجة واحدة |
| CQRS | فصل الـ Commands عن الـ Queries |
| Repository Pattern | abstraction لـ data access |
| Unit of Work | إدارة الـ transactions |
| Layer Communication | إزاي الـ layers بتتكلم مع بعض |
| Vertical Slice Architecture | بديل حديث للـ layered architecture |
| Feature Folders | تنظيم الكود حول الـ features |

---

### 09 — Design Patterns

**لماذا مهم؟**  
بيخليك تتكلم بنفس اللغة مع أي developer وتحل مشاكل متكررة بطريقة صح ومعروفة.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Factory & Abstract Factory | إنشاء objects بدون تحديد الـ concrete type |
| Strategy Pattern | تبديل الخوارزمية في runtime |
| Builder Pattern | بناء objects معقدة step-by-step |
| Observer / Event-Driven | إشعار المشتركين عند حدوث events |
| Mediator Pattern | تقليل الـ coupling بين الـ components |
| Decorator & Pipeline | إضافة behavior بدون تعديل الـ class |
| Specification Pattern | تغليف business rules في classes |
| Outbox Pattern | ضمان إرسال الـ messages بشكل موثوق |

---

### 10 — Testing ⭐ مضاف

**لماذا مهم؟**  
مش اختياري. أي شغل حقيقي بيطلب tests. TDD بيخليك تكتب كود أحسن من الأول.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Unit Testing | xUnit / NUnit — اختبار الـ units المعزولة |
| Test Structure | Arrange, Act, Assert |
| Mocking | Moq / NSubstitute — استبدال الـ dependencies |
| Integration Testing | اختبار الـ components مع بعض |
| TestContainers | تشغيل real DB في الـ tests |
| TDD | اكتب الـ test الأول، ثم الـ implementation |
| Code Coverage | قياس نسبة الكود المغطى |
| Snapshot Testing | اختبار الـ output بدون hard-coded assertions |

---

## المرحلة 4 — Runtime & Frameworks

> هنا بتشتغل مع الـ runtime الحقيقي وتتحكم في الأداء.

---

### 11 — Async Programming

**لماذا مهم؟**  
الـ async مش معناه thread جديد. ده نقطة ناس كتير بتفهمها غلط وبتعمل deadlocks من غير ما تعرف.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| `async` / `await` | الآلية الحقيقية من الداخل |
| `Task` vs `Task<T>` | الفرق والاستخدام الصح |
| Async State Machine | إزاي الـ compiler بيحوّل الكود |
| Thread Pool | إزاي بيشتغل وبيوزّع الشغل |
| `Task.WhenAll` & `WhenAny` | تشغيل مهام متوازية |
| `CancellationToken` | إلغاء العمليات بشكل نظيف |
| `ConfigureAwait(false)` | متى وليه تستخدمه |
| Deadlocks | إزاي بتحصل وإزاي تتجنبها |
| `ValueTask` | متى تستخدمها بدل `Task` |

---

### 12 — Multithreading & Concurrency

**لماذا مهم؟**  
لازم تفهمه عشان تبني systems بتتحمل آلاف requests وparallel execution.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Thread vs Task | الفرق الجوهري |
| Locks & Monitor | حماية الـ shared resources |
| `Interlocked` | atomic operations بدون locks |
| `ConcurrentDictionary` / `Queue` | thread-safe collections |
| Race Conditions | إزاي بتحصل وإزاي تكتشفها |
| Deadlocks في Threading | التشخيص والحل |
| `ReaderWriterLockSlim` | قراءة متوازية، كتابة حصرية |
| `Semaphore` & `SemaphoreSlim` | تحديد عدد الـ concurrent operations |

---

### 13 — Memory Management

**لماذا مهم؟**  
هنا بتشوف ليه برنامج سريع وبرنامج بطيء. فهم الـ GC بيخليك تكتب كود مختلف تماماً.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Stack vs Heap | الفرق الحقيقي وأين يعيش كل object |
| Garbage Collector | الثلاث أجيال وكيفية عملها |
| Boxing / Unboxing | التكلفة الخفية |
| `IDisposable` Pattern | تحرير الـ unmanaged resources |
| Finalizer | متى تستخدمه (نادراً) |
| `using` statement & declaration | ضمان تحرير الـ resources |
| `Span<T>` و`Memory<T>` | الوصول للذاكرة بدون allocations |
| `ArrayPool<T>` | إعادة استخدام الـ arrays |
| GC Pauses | إزاي تقللها في الـ production |

---

### 14 — Caching & Messaging ⭐ مضاف

**لماذا مهم؟**  
أي system حقيقي بيستخدمهم. من غيرهم مش هتعرف تبني distributed systems ولا تتحمل load حقيقي.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| In-Memory Cache | الـ caching داخل الـ process |
| `IDistributedCache` | واجهة موحدة للـ distributed caching |
| Redis | الأوامر الأساسية وأهم الـ patterns |
| Cache-Aside Pattern | الـ pattern الأكثر شيوعاً |
| Cache Invalidation Strategies | إزاي تبطل الـ cache صح |
| RabbitMQ | الـ exchanges والـ queues والـ bindings |
| Message Patterns | Pub/Sub, Work Queue, Request/Reply |
| Kafka | متى تستخدمه وليه (vs RabbitMQ) |
| Outbox Pattern | ضمان إرسال الـ messages مع الـ transactions |

---

### 15 — EF Core Advanced + ASP.NET Core Internals

**لماذا مهم؟**  
معظم الـ performance issues في الـ backend بتيجي من استخدام EF Core غلط. وفهم ASP.NET من الداخل بيخلي الـ debugging سهل.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| Change Tracking | إزاي EF بيتتبع التغييرات وإمتى بيتأثر الأداء |
| `AsNoTracking()` | تحسين الأداء في الـ read-only queries |
| Eager / Lazy / Explicit Loading | الفرق والاستخدام الصح لكل واحد |
| Compiled Queries | للـ hot paths اللي بتتنفذ كتير |
| Query Optimization | فهم الـ SQL المولّد وتحسينه |
| Middleware Pipeline | ترتيب التنفيذ والتأثير على الـ request |
| Filters | Action Filters / Result Filters / Exception Filters |
| Model Binding | إزاي الـ request data بيتحول لـ objects |
| Routing Internals | كيفية اختيار الـ action المناسب |
| Auth Flow | Authentication & Authorization من الداخل |

---

## المرحلة 5 — Low-Level Mastery

> المرحلة النهائية لمن يريد إتقان C# على مستوى Expert.

---

### 16 — CLR / IL / JIT

**لماذا مهم؟**  
هنا بتفهم إزاي الكود بيتحول من C# → IL → Machine Code. بداية فهم الـ runtime الحقيقي.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| CLR | Common Language Runtime — بيعمل إيه بالظبط |
| CTS | Common Type System — نظام الـ types الموحّد |
| Assemblies | الـ structure وإزاي بتتحمّل |
| Metadata | إزاي الـ runtime بيقرأ معلومات الـ types |
| IL (Intermediate Language) | اللغة الوسيطة بين C# والـ machine code |
| JIT Compiler | مراحل الـ compilation |
| Tiered Compilation | الـ optimization التدريجي (.NET 6+) |
| AOT Compilation | Ahead-of-Time vs JIT |
| GC Internals | الأجيال والـ large object heap |

---

### 17 — Low-Level C# & Performance Engineering

**لماذا مهم؟**  
مرحلة الـ advanced جداً. لما تكتب ultra high-performance systems أو game engines أو realtime systems.

**المواضيع:**

| الموضوع | الوصف |
|--------|-------|
| `unsafe` keyword | تعطيل الـ memory safety للأداء |
| Pointer Arithmetic | التعامل المباشر مع الذاكرة |
| `stackalloc` | تخصيص memory على الـ stack مباشرةً |
| `ref struct` | structures تعيش على الـ stack فقط |
| `Span<T>` و`Memory<T>` بعمق | الـ slices والـ windows على الذاكرة |
| SIMD | تنفيذ عمليات متوازية على الـ CPU |
| P/Invoke | استدعاء الـ native code (C/C++) |
| Native Interop | التكامل مع الـ unmanaged code |
| Memory Pools & Zero Allocation | كتابة كود بدون أي GC pressure |

---

## خريطة التسلسل الكاملة

```
المرحلة 1 — الأساس الحقيقي
├── 01. OOP & SOLID
├── 02. Delegates / Lambdas / Functional
└── 03. Generics Advanced
            ↓
المرحلة 2 — فهم الـ Magic
├── 04. LINQ Deep Dive
├── 05. Expression Trees
└── 06. Reflection
            ↓
المرحلة 3 — Architecture & Systems
├── 07. Dependency Injection
├── 08. Clean Architecture
├── 09. Design Patterns
└── 10. Testing ⭐
            ↓
المرحلة 4 — Runtime & Frameworks
├── 11. Async Programming
├── 12. Multithreading & Concurrency
├── 13. Memory Management
├── 14. Caching & Messaging ⭐
└── 15. EF Core Advanced + ASP.NET Core Internals
            ↓
المرحلة 5 — Low-Level Mastery
├── 16. CLR / IL / JIT
└── 17. Low-Level C# & Performance Engineering
```

---

## ملاحظات مهمة

- **⭐ المواضيع المضافة:** Testing (10) وCaching & Messaging (14) مواضيع جديدة تم إضافتها لأهميتها الكبيرة في بيئة العمل الحقيقية.
- **الترتيب مهم:** كل مرحلة مبنية على السابقة. لا تتجاوز المراحل.
- **التطبيق العملي:** قراءة المفاهيم وحدها غير كافية — كوّد مشروع حقيقي بعد كل مرحلة.
- **المرحلة الأخيرة اختيارية:** المرحلة 5 موجّهة لمن يعمل على systems تتطلب أداء استثنائي.

---

*تم توليد هذا الـ README من roadmap تفاعلية لتطوير الـ C# Backend.*
