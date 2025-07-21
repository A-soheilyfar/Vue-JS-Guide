# Vue-JS-Guide
Just a Vue JS Guide

<div dir="rtl">
Vue.js یک فریمورک جاوااسکریپت برای ساختن رابط کاربری (User Interface) وب‌سایت‌ها و اپلیکیشن‌هاست.

رابط کاربری (UI): همون قسمتی از سایت یا اپلیکیشنه که کاربر می‌بینه و باهاش کار می‌کنه. دکمه‌ها، فرم‌ها، منوها، متن‌ها؛ همه‌ی این‌ها می‌شن رابط کاربری. Vue به تو کمک می‌کنه این بخش‌های دیداری رو خیلی راحت و هوشمند بسازی. 👨‍🎨

فریمورک (Framework): یعنی یک چارچوب و مجموعه قوانین از پیش آماده شده. به جای اینکه برای ساختن یک ساختمان از صفر آجر روی آجر بذاری، فریمورک بهت یک اسکلت آماده می‌ده که فقط باید دیوارها و دکوراسیون داخلی رو بهش اضافه کنی. این کارت رو سریع‌تر و منظم‌تر می‌کنه.



کار اصلی Vue چیه؟
Vue میاد داده‌ها (Data) و منطق جاوااسکریپتی تو رو به کدهای HTML وصل می‌کنه. جادوی Vue اینجاست که هر وقت اون داده‌ها تغییر کنن، HTML هم به‌صورت خودکار آپدیت می‌شه. به این قابلیت میگن واکنش‌گرایی (Reactivity).


## نحوه نصب (روش مدرن و استاندارد)
امروزه بهترین و ساده‌ترین راه برای شروع یک پروژه Vue استفاده از ابزار رسمی خود Vue به نام create-vue هست. برای این کار باید Node.js روی سیستمت نصب باشه.

باز کردن ترمینال: ترمینال یا Command Prompt (در ویندوز) یا Terminal (در مک و لینوکس) رو باز کن.

اجرای دستور نصب: دستور زیر رو کپی و در ترمینال وارد کن و Enter رو بزن:
</div>



```bash
npm create vue@latest
```
<div dir="rtl">
رفتن به پوشه پروژه و نصب پکیج‌ها: بعد از اینکه پروژه‌ات ساخته شد، ترمینال بهت سه تا دستور دیگه می‌ده که باید به ترتیب اجرا کنی:
</div>

```
# 1. به پوشه پروژه‌ای که ساختی برو (اسم پروژه رو جایگزین کن)
cd <your-project-name>

# 2. پکیج‌های مورد نیاز رو نصب کن
npm install

# 3. پروژه رو اجرا کن تا بتونی توی مرورگر ببینیش
npm run dev
```
<div dir="rtl">

بعد از اجرای npm run dev، یک آدرس مثل http://localhost:5173 بهت می‌ده که اگه توی مرورگر بازش کنی، اولین اپلیکیشن Vue خودت رو می‌بینی! 🥳


حالا بریم سراغ اون فایل‌ها و کدهای گیج‌کننده‌ای که ساخته می‌شن. سه بخش اصلی وجود داره که باید بشناسیشون.

### ۱. نقطه اتصال: index.html و <div id="app"> 
توی پوشه اصلی پروژه‌ات یک فایل index.html وجود داره. این تنها فایل HTML واقعی سایت توئه. اگه بازش کنی، داخل تگ <body> یه همچین چیزی می‌بینی:
</div>

```html
<div id="app"></div>
```
<div dir="rtl">

### ۲. موتور اصلی: `src/main.js` 
### این فایل، موتور روشن‌کننده اپلیکیشن توئه. دو خط کد اصلی داخلش این‌ها هستن:
</div>

```js
import { createApp } from 'vue'
import App from './App.vue'
createApp(App).mount('#app')
```
<div dir="rtl">

  - import App from './App.vue': میگه کامپوننت اصلی ما فایلی به نام App.vue است.

  - createApp(App): یعنی "یک اپلیکیشن Vue بر اساس کامپوننت App بساز."

  - .mount('#app'): این همون دستور نهاییه! میگه "حالا اون اپلیکیشنی که ساختی رو بردار و به عنصری که id="app" داره (همون div در index.html) متصل کن."

### ۳. کامپوننت اصلی: `src/App.vue`

این فایل قلب تپنده اپلیکیشن تو و جاییه که بیشتر کدهات رو می‌نویسی. فایل‌های با پسوند .vue به کامپوننت‌های تک‌فایلی (Single-File Components) معروفن. یعنی HTML، جاوااسکریپت و CSS مربوط به یک بخش از رابط کاربری، همگی در یک فایل کنار هم قرار دارن. 🧱

یک فایل `App.vue` سه بخش اصلی داره:
</div>


```vue
<template>
  <header>
    <h1>سلام دنیا!</h1>
  </header>
</template>

<script setup>
// اینجا منطق برنامه رو می‌نویسی
// مثلاً داده‌ها، متدها و...
</script>

<style scoped>
h1 {
  color: green;
}
</style>

```
<div dir="rtl">
  `<template>` : هرچیزی که کاربر قراره ببینه (ساختار HTML کامپوننت) اینجا قرار می‌گیره.

  `<script setup>` : مغز کامپوننت. داده‌ها، توابع و تمام منطق جاوااسکریپتی اینجا نوشته می‌شه.

 `<style scoped>` : کدهای CSS برای خوشگل کردن کامپوننت. کلمه scoped خیلی مهمه، چون باعث می‌شه این استایل‌ها فقط روی همین کامپوننت اعمال بشن و روی بقیه بخش‌های سایت تأثیر نذارن.


  خلاصه کل داستان:
`main.js` کامپوننت `App.vue` رو برمی‌داره، اون رو به یک اپلیکیشن کامل تبدیل می‌کنه و در نهایت کل اپلیکیشن رو داخل `<div id="app">` در فایل index.html "تزریق" یا mount می‌کنه تا در مرورگر قابل دیدن باشه.



### واکنشگرایی (Reactivity) در Vue
واکنش‌گرایی یعنی وقتی داده‌های شما در بخش <script> تغییر می‌کنند، بخش <template> (یا همان ظاهر سایت) به صورت خودکار و بدون نیاز به رفرش صفحه، آپدیت می‌شود. Vue این کار را از طریق چند ابزار کلیدی انجام می‌دهد که در کد شما استفاده شده‌اند.


### ref
`ref` یک تابع در Vue است که به شما اجازه می‌دهد یک متغیر "واکنش‌گرا" یا `reactive` بسازید.

کاربرد: وقتی می‌خواهید یک مقدار (مثل یک رشته متن، عدد یا حتی یک آبجکت) داشته باشید که با تغییر آن، ظاهر برنامه هم تغییر کند، از ref استفاده می‌کنید.

نحوه کار: ref مقدار شما را در یک آبجکت خاص قرار می‌دهد. برای دسترسی به مقدار اصلی در بخش `<script>` باید از .value استفاده کنید. اما در بخش `<template>`، ویو به صورت هوشمند این کار را برای شما انجام می‌دهد و نیازی به .value نیست.
javascript
```javascript

import {ref} from 'vue'
const appName = ref("My new task manager")
```
اینجا appName یک رفرنس واکنش‌گرا است. اگر بخواهید در یک تابع جاوااسکریپتی آن را تغییر دهید، باید بنویسید: `appName.value = "New Title".`
مثال
```vue
<script setup>
import {ref} from 'vue'
// const appName="My new task manager"

const appName = ref("My new task manager")
// alert(appName);   did not output the resulst
alert(appName.value)
```

#### ref for primitives
مشابه بالا برای داده های عادی
#### ref for arrays
اینحا باید از reactive استفاده کنیم بنابراین به پروژه اضافه میکنیم
```vue
script setup>
import {ref,reactive} from 'vue'
```
و سپس برای این آرایه مینویسیم
‍‍‍```vue
task = ['a','b','c']
const task = reactive(['a','b','c'])



در v-for, ویژگی key یک شناسه منحصر به فرد برای هر آیتم در لیست است. این به Vue کمک می‌کند تا بفهمد هر آیتم در لیست داده‌ها دقیقاً با کدام عنصر در صفحه (DOM) مطابقت دارد.

به زبان ساده، key مثل شماره پلاک برای ماشین‌ها یا کد ملی برای افراد عمل می‌کند.

چرا key ضروری است؟
وقتی لیست شما تغییر می‌کند (مثلاً یک آیتم اضافه، حذف یا جابجا می‌شود)، Vue باید بفهمد که چگونه صفحه را به بهینه‌ترین شکل ممکن به‌روزرسانی کند.

ردیابی هویت (Identity Tracking):
key به Vue اجازه می‌دهد تا هر آیتم را به طور دقیق ردیابی کند. وقتی ترتیب لیست عوض می‌شود، Vue به جای اینکه محتوای عناصر را تغییر دهد، خود عناصر را جابجا می‌کند که بسیار بهینه‌تر است.

جلوگیری از باگ‌های غیرمنتظره:
بدون key، اگر ترتیب آیتم‌ها تغییر کند، Vue ممکن است دچار خطا شود. برای مثال، اگر لیستی از فیلدهای ورودی (<input>) داشته باشید و آیتم دوم را حذف کنید، ممکن است متنی که در فیلد سوم تایپ کرده بودید، به اشتباه در فیلد دوم باقی بماند. key این مشکل را با اطمینان از اینکه هر داده به عنصر صحیح خود متصل است، حل می‌کند.



#### بهترین روش برای انتخاب key چیست؟
✅ بهترین انتخاب: یک مقدار منحصر به فرد و ثابت برای هر آیتم. معمولاً این مقدار، id آیتم است که از دیتابیس می‌آید.

```vue
<div v-for="item in items" :key="item.id">
  {{ item.text }}
</div>
```
#### ❌ انتخاب‌های نامناسب:

استفاده از index: استفاده از index آرایه به عنوان key (:key="index") توصیه نمی‌شود، مگر اینکه لیست شما کاملاً ثابت باشد و هیچ‌گاه ترتیب آن عوض نشود یا آیتمی از وسط آن حذف/اضافه نگردد. زیرا با تغییر ترتیب لیست، index ها نیز تغییر کرده و Vue دچار همان سردرگمی می‌شود.

استفاده از خود آبجکت (:key="task"): کاری که شما در کدتان انجام داده‌اید، یعنی استفاده از خود آبجکت به عنوان key، در Vue 3 کار می‌کند اما بهترین روش نیست. همیشه استفاده از یک شناسه ساده و یکتا (مثل عدد یا رشته) اولویت دارد.

خلاصه: key برای عملکرد صحیح و بهینه v-for حیاتی است. همیشه سعی کنید یک شناسه منحصر به فرد و پایدار برای آن فراهم کنید.


#### یک مثال کامل و خوب برای نمایش آرایه‌ای از اطلاعات در باکس‌های مجزا با استفاده از reactive، v-for و key

این کد یک کامپوننت کامل Vue است که می‌توانید آن را مستقیماً استفاده کنید.

```vue
<script setup>
import { reactive } from 'vue'

// با استفاده از reactive، یک آبجکت state می‌سازیم که شامل آرایه‌ی ماست.
// کل این آبجکت و آرایه‌ی درون آن واکنش‌گرا (reactive) خواهند بود.
const state = reactive({
  features: [
    {
      id: 1,
      icon: '🎨',
      title: 'طراحی مدرن',
      description: 'طراحی‌های جذاب و کاربرپسند بر اساس آخرین ترندهای روز دنیا.'
    },
    {
      id: 2,
      icon: '💻',
      title: 'توسعه واکنش‌گرا',
      description: 'نمایش بی‌نقص وب‌سایت شما در تمام دستگاه‌ها، از موبایل تا دسکتاپ.'
    },
    {
      id: 3,
      icon: '🚀',
      title: 'بهینه‌سازی سرعت',
      description: 'بارگذاری سریع صفحات برای بهبود تجربه کاربری و رتبه بهتر در موتورهای جستجو.'
    }
  ]
})
</script>

<template>
  <div class="features-container">
    <div v-for="feature in state.features" :key="feature.id" class="feature-box">
      <div class="icon">{{ feature.icon }}</div>
      <h3>{{ feature.title }}</h3>
      <p>{{ feature.description }}</p>
    </div>
  </div>
</template>

<style scoped>
.features-container {
  display: flex;
  justify-content: center;
  gap: 20px; /* فاصله بین باکس‌ها */
  flex-wrap: wrap; /* برای نمایش بهتر در صفحه‌های کوچک */
  padding: 20px;
  font-family: sans-serif;
}

.feature-box {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 20px;
  width: 250px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s;
}

.feature-box:hover {
  transform: translateY(-5px); /* افکت شناور شدن باکس */
}

.feature-box .icon {
  font-size: 40px;
  margin-bottom: 15px;
}

.feature-box h3 {
  color: #333;
  margin-bottom: 10px;
}

.feature-box p {
  color: #666;
  font-size: 14px;
  line-height: 1.6;
}
</style>

```

`{{ }} (Text Interpolation)`
این علامت که به آن "Mustache syntax" هم می‌گویند، ساده‌ترین راه برای نمایش داده‌های واکنش‌گرا در HTML است. به این کار "اتصال داده یک‌طرفه" (One-way data binding) می‌گویند، چون داده فقط از `<script>` به `<template>` می‌رود.

کاربرد: نمایش محتوای یک متغیر جاوااسکریپت در تگ‌های HTML.

نحوه کار: هر چیزی که داخل `{{ }}` قرار بگیرد، با مقدار متغیر همنامش در `<script>` جایگزین می‌شود و هر وقت آن متغیر تغییر کند، این قسمت هم خودکار آپدیت می‌شود.
```vue
<h1>
  {{appName}}
</h1>
```
این کد مقدار appName را در تگ `<h1>` نمایش می‌دهد. در ابتدا، "My new task manager" را نشان می‌دهد. اگر appName تغییر کند، این عنوان هم فوراً عوض می‌شود.


### v-model
v-model برای ایجاد "اتصال داده دوطرفه" (Two-way data binding) استفاده می‌شود، معمولاً روی تگ‌های فرم مثل `<input>, <textarea> و <select>.`

کاربرد: همگام‌سازی مقدار یک فیلد ورودی با یک متغیر واکنش‌گرا.

نحوه کار: v-model دو کار را همزمان انجام می‌دهد:

مقدار متغیر (appName) را در فیلد` <input>` نمایش می‌دهد.

هر وقت کاربر چیزی در `<input>` تایپ کند، مقدار متغیر appName را فوراً آپدیت می‌کند.

```html <input type="text" v-model="appName">```

این کد یک ارتباط زنده و دوطرفه بین فیلد ورودی و متغیر appName برقرار می‌کند:

وقتی صفحه بارگذاری می‌شود، این فیلد ورودی مقدار "My new task manager" را نشان می‌دهد.

اگر شما در این فیلد تایپ کنید و آن را به "My Awesome Tasks" تغییر دهید، متغیر appName هم فوراً به همین مقدار جدید آپدیت می‌شود.

چون appName آپدیت شده، تگ `<h1>{{appName}}</h1>` هم بلافاصله "My Awesome Tasks" را نمایش می‌دهد. ✅

این سه مفهوم در کنار هم، هسته‌ی اصلی واکنش‌گرایی در Vue را تشکیل می‌دهند و به شما اجازه می‌دهند به سادگی برنامه‌های پویا و تعاملی بسازید.

### ساخت کامپوننت جدا از مثال قبلی
 برای ساخت کامپوننت‌های قابل استفاده مجدد (reusable) ما مثال قبلی را به دو فایل تقسیم می‌کنیم: App.vue به عنوان والد و FeaturesContainer.vue به عنوان فرزند. 
 ##### بنابراین محتوای features-container رو به داخل یک پوشه جدا در components به همین نام میذاریم

ابتدا، ساختار پوشه‌ها به این شکل خواهد بود:
```less
src/
├── components/
│   └── FeaturesContainer.vue  (کامپوننت فرزند)
└── App.vue                    (کامپوننت والد)
```
#### ۱. کامپوننت والد (App.vue)
این کامپوننت داده‌ها را در خود نگه می‌دارد و آن‌ها را از طریق prop به کامپوننت فرزند ارسال می‌کند.
```vue
<script setup>
import { reactive } from 'vue'
// 1. کامپوننت فرزند را وارد می‌کنیم
import FeaturesContainer from './components/FeaturesContainer.vue'

// 2. داده‌ها همچنان در کامپوننت والد تعریف می‌شوند
const state = reactive({
  features: [
    {
      id: 1,
      icon: '🎨',
      title: 'طراحی مدرن',
      description: 'طراحی‌های جذاب و کاربرپسند بر اساس آخرین ترندهای روز دنیا.'
    },
    {
      id: 2,
      icon: '💻',
      title: 'توسعه واکنش‌گرا',
      description: 'نمایش بی‌نقص وب‌سایت شما در تمام دستگاه‌ها، از موبایل تا دسکتاپ.'
    },
    {
      id: 3,
      icon: '🚀',
      title: 'بهینه‌سازی سرعت',
      description: 'بارگذاری سریع صفحات برای بهبود تجربه کاربری و رتبه بهتر در موتورهای جستجو.'
    }
  ]
})
</script>

<template>
  <main>
    <h1>ویژگی‌های ما</h1>
    <FeaturesContainer :featuresList="state.features" />
  </main>
</template>

<style>
/* استایل‌های عمومی می‌توانند اینجا باشند */
main {
  text-align: center;
  font-family: sans-serif;
}
</style>
```
#### ۲. کامپوننت فرزند (FeaturesContainer.vue)
این کامپوننت داده‌ها را از والد دریافت می‌کند و وظیفه‌ی نمایش آن‌ها را بر عهده دارد. این کامپوننت هیچ داده‌ای از خودش ندارد و کاملاً به prop دریافتی وابسته است.
```vue
<script setup>
import { defineProps } from 'vue'

// 1. با defineProps مشخص می‌کنیم که این کامپوننت منتظر دریافت یک prop به نام 'featuresList' است.
const props = defineProps(['featuresList'])

// نکته: روش بهتر و دقیق‌تر برای تعریف props به صورت آبجکت است:
// defineProps({
//   featuresList: {
//     type: Array,
//     required: true
//   }
// })
</script>

<template>
  <div class="features-container">
    <div v-for="feature in featuresList" :key="feature.id" class="feature-box">
      <div class="icon">{{ feature.icon }}</div>
      <h3>{{ feature.title }}</h3>
      <p>{{ feature.description }}</p>
    </div>
  </div>
</template>

<style scoped>
/* تمام استایل‌های مربوط به باکس‌ها به اینجا منتقل شده‌اند */
.features-container {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  padding: 20px;
}

.feature-box {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 20px;
  width: 250px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s;
}

.feature-box:hover {
  transform: translateY(-5px);
}

.feature-box .icon {
  font-size: 40px;
  margin-bottom: 15px;
}

.feature-box h3 {
  color: #333;
  margin-bottom: 10px;
}

.feature-box p {
  color: #666;
  font-size: 14px;
  line-height: 1.6;
}
</style>

```
<div dir="rtl">

  


## این ساختار چگونه کار می‌کند؟
App.vue (والد): مسئول اصلی داده‌هاست. آرایه features را می‌سازد.

ارسال Prop: کامپوننت App.vue با استفاده از سینتکس :featuresList="state.features"، کل آرایه را به عنوان یک "ویژگی" یا prop به کامپوننت فرزند پاس می‌دهد.

FeaturesContainer.vue (فرزند): این کامپوننت کاملاً " نمایشی" (Presentational) است.

دریافت Prop: با استفاده از defineProps(['featuresList'])، کامپوننت فرزند اعلام می‌کند که یک ورودی به نام featuresList دریافت خواهد کرد.

نمایش داده: حلقه v-for حالا به جای اینکه روی داده‌ی محلی اجرا شود، روی prop دریافتی (featuresList) اجرا شده و باکس‌ها را بر اساس آن می‌سازد.

این الگو به شما اجازه می‌دهد FeaturesContainer را در هر جای دیگری از برنامه با هر آرایه‌ی دیگری که ساختار مشابهی داشته باشد، مجدداً استفاده کنید.
</div>



 ## چرا نمی‌توانیم prop را مستقیم تغییر دهیم؟
تصور کنید کامپوننت والد (مثلاً App.vue) یک "مدیر" است و کامپوننت فرزند (Task.vue) یک "کارمند".

دستور از بالا به پایین (Props): مدیر (والد) به کارمند (فرزند) یک دستور کار می‌دهد. این دستور کار همان prop است. در مثال شما، والد به فرزند می‌گوید: «این تسک را بگیر (task) که وضعیت فعلی آن completed: false است.»

تغییر غیرمجاز: حالا اگر کارمند (فرزند) سرخود تصمیم بگیرد و روی برگه دستور کار بنویسد «انجام شد» و وضعیت آن را تغییر دهد، مدیر اصلی (والد) از این تغییر خبردار نمی‌شود. در دنیای واقعی، این کار باعث ناهماهنگی و بی‌نظمی می‌شود.

در Vue هم همین‌طور است:

منبع اصلی داده (Source of Truth) در کامپوننت والد قرار دارد.

فرزند فقط داده را به عنوان prop دریافت می‌کند تا نمایش دهد.

اگر فرزند مستقیماً prop را تغییر دهد، والد متوجه نمی‌شود و این قانون "جریان داده یک‌طرفه" را نقض می‌کند. Vue برای جلوگیری از این بی‌نظمی، به شما خطا می‌دهد یا تغییر اعمال نمی‌شود.


 ## راه حل صحیح: گزارش دادن به مدیر (Emit کردن Event)
راه درست این است که کارمند (فرزند) به مدیر (والد) اطلاع دهد که تغییری لازم است. این اطلاع‌رسانی از طریق ارسال یک رویداد (Event) انجام می‌شود.



## مثال کامل: والد و فرزند
بیایید یک مثال کامل از والد (TodoList.vue) و فرزند (Task.vue) ببینیم.

#### 1. کامپوننت فرزند (Task.vue)
این کامپوننت مسئول نمایش یک تسک و اطلاع‌رسانی برای تغییر وضعیت است.
```vue
<script setup>
  // 1. تسک را به عنوان prop دریافت می‌کند
  const props = defineProps(['task'])

  // 2. رویدادی که قرار است به والد ارسال شود را تعریف می‌کند
  const emit = defineEmits(['toggle-status'])
</script>

<template>
  <div class="task">
    <h3>{{ task.name }}</h3>
    <div class="task-check">
      <input 
        type="checkbox" 
        :checked="task.completed"
        
        @change="emit('toggle-status', task.id)" 
      />
      <label>Done</label>
    </div>
  </div>
</template>
```
#### 2. کامپوننت والد (TodoList.vue)
این کامپوننت لیست تسک‌ها را مدیریت می‌کند و به رویدادهای فرزند گوش می‌دهد.

```vue
<script setup>
  import { ref } from 'vue'
  import Task from './Task.vue' // کامپوننت فرزند را وارد می‌کنیم

  // 1. منبع اصلی داده‌ها (State) در والد قرار دارد
  const tasks = ref([
    { id: 1, name: 'یادگیری Vue', completed: false },
    { id: 2, name: 'نوشیدن قهوه', completed: true },
    { id: 3, name: 'استراحت کردن', completed: false }
  ])

  // 3. این متد زمانی اجرا می‌شود که رویداد 'toggle-status' از فرزند دریافت شود
  function handleToggleStatus(taskId) {
    // تسک مورد نظر را پیدا می‌کند
    const taskToUpdate = tasks.value.find(t => t.id === taskId)
    
    // و وضعیت آن را در داده اصلی (که متعلق به والد است) تغییر می‌دهد
    if (taskToUpdate) {
      taskToUpdate.completed = !taskToUpdate.completed
    }
  }
</script>

<template>
  <h1>لیست کارهای من</h1>
  <div v-for="task in tasks" :key="task.id">
    <Task :task="task" @toggle-status="handleToggleStatus" />
  </div>
</template>

```
<div dir="rtl">
emit در Vue یک سیستم پیام‌رسانی است که به کامپوننت فرزند (Child) اجازه می‌دهد با کامپوننت والد (Parent) خود صحبت کند.

تصور کنید emit مانند یک "زنگ" یا "اعلان" است. فرزند نمی‌تواند مستقیماً داده‌های والد را تغییر دهد (چون این کار باعث بی‌نظمی می‌شود)، اما می‌تواند زنگ را به صدا درآورد تا به والد بگوید: «یک اتفاقی افتاده، لطفاً شما کاری انجام بده!»

## چرا به emit نیاز داریم؟ (قانون جریان داده یک‌طرفه)
در Vue، داده‌ها همیشه از بالا به پایین جریان دارند:

والد به فرزند (Props 🔽): والد از طریق props به فرزند داده می‌دهد.

فرزند به والد (Events 🔼): فرزند نباید مستقیماً آن prop را تغییر دهد. در عوض، باید یک رویداد (event) را به سمت بالا emit (منتشر) کند تا به والد اطلاع دهد که تغییری لازم است.

این قانون باعث می‌شود که همیشه بدانیم منبع اصلی تغییرات کجاست (در والد) و دیباگ کردن کد بسیار آسان‌تر شود.
</div>

## emit چطور کار می‌کند؟ (یک مثال ساده)
بیایید یک مثال خیلی ساده را در نظر بگیریم: یک کامپوننت والد که یک عدد را نمایش می‌دهد و یک کامپوننت فرزند که یک دکمه برای افزایش آن عدد دارد.

#### مرحله ۱: فرزند (ButtonComponent.vue) زنگ را آماده می‌کند
فرزند ابتدا باید اعلام کند که چه نوع "زنگ" یا رویدادی را می‌تواند به صدا درآورد.
```vue

<script setup>
// 1. تعریف می‌کنیم که این کامپوننت می‌تواند رویدادی به نام 'increase-count' را emit کند
const emit = defineEmits(['increase-count'])
</script>

<template>
  <button @click="emit('increase-count')">
    افزایش بده
  </button>
</template>

```
defineEmits: به Vue می‌گوید که این کامپوننت چه رویدادهایی را ارسال خواهد کرد.

`emit('increase-count'):` این همان به صدا درآوردن زنگ است.

#### مرحله ۲: والد (Counter.vue) به زنگ گوش می‌دهد
والد کامپوننت فرزند را در تمپلیت خود قرار می‌دهد و مشخص می‌کند که اگر زنگ increase-count به صدا درآمد، چه کاری باید انجام دهد.

```vue
<script setup>
import { ref } from 'vue'
import ButtonComponent from './ButtonComponent.vue'

// داده اصلی در والد قرار دارد
const count = ref(0)

// 3. این تابع زمانی اجرا می‌شود که رویداد از فرزند دریافت شود
function handleIncrease() {
  count.value++
}
</script>

<template>
  <h1>شمارنده: {{ count }}</h1>
  
  <ButtonComponent @increase-count="handleIncrease" />
</template>
```


```js
// عدد 5 را همراه با رویداد ارسال می‌کنیم
emit('increase-by', 5)
```
#### (والد)
```vue
<script setup>
function handleIncrease(amount) { // مقدار 5 اینجا دریافت می‌شود
  count.value += amount
}
</script>

<template>
  <ButtonComponent @increase-by="handleIncrease" />
</template>

```


## جمع‌بندی
Prop (داده به پایین 🔽): والد از طریق :task="task" داده را به فرزند می‌دهد.

Emit (رویداد به بالا 🔼): فرزند از طریق @toggle-status="handleToggleStatus" به والد اطلاع می‌دهد که تغییری رخ داده است.

State Management (مدیریت در والد 🧠): والد مسئول نهایی تغییر دادن داده‌هاست.

این الگو باعث می‌شود کد شما بسیار خواناتر، قابل پیش‌بینی‌تر و برای دیباگ کردن آسان‌تر باشد.


-‍‍------

***

ــــــــــــ


## داستان Mount در Vue 3: از ایده تا نمایش 🚀
تصور کن یه ایده عالی برای یه اپلیکیشن وب داری. با Vue 3 شروع به کدنویسی می‌کنی و کلی کامپوننت‌ خفن می‌سازی. این کامپوننت‌ها مثل قطعات لگو هستن: به تنهایی وجود دارن ولی هنوز به هم وصل نشدن و کسی نمی‌تونه اون‌ها رو ببینه. اینجا قهرمان داستان ما، یعنی mount وارد می‌شه.
mount در واقع پلیه بین دنیای مجازی Vue (کدهات) و دنیای واقعی مرورگر (صفحه‌ای که کاربر می‌بینه). تا وقتی که mount رو صدا نزنی، اپلیکیشن تو فقط در حافظه وجود داره و هیچ اثری ازش روی صفحه نیست.


## mount 
دستور شروع و نمایش اپلیکیشن Vue در مرورگره.

## beforeMount 
درست قبل از نمایش، وقتی همه چیز در حافظه آمادست، اجرا می‌شه.

## mounted 
درست بعد از اینکه اپلیکیشن روی صفحه نمایش داده شد و قابل دیدن بود، اجرا می‌شه و بهترین مکان برای دستکاری مستقیم DOM است.
</div>


مثال کاربردی برای beforeMount
فرض کنید می‌خواهیم قبل از نمایش کامپوننت، یک سری داده را از یک منبع خارجی (مثلاً یک API) فراخوانی کنیم. اما نمی‌خواهیم این کار را در setup یا created انجام دهیم، چون می‌خواهیم تا آخرین لحظه‌ی ممکن قبل از رندر شدن صبر کنیم.

در این مثال، ما یک تایمر ساده را شبیه‌سازی می‌کنیم که قبل از mount شدن، یک مقدار را تنظیم می‌کند.



```html
  <!DOCTYPE html>
  <html lang="fa" dir="rtl">
  <head>
      <title>مثال beforeMount</title>
      <script src="https://unpkg.com/vue@3"></script>
      <style>
          #app {
              padding: 20px;
              border: 2px solid #42b983;
              border-radius: 8px;
              text-align: center;
          }
      </style>
  </head>
  <body>
  
  <div id="app"></div>
  
  <script>
      const { createApp, ref, onBeforeMount, onMounted } = Vue;
  
      createApp({
          setup() {
              // یک ref برای دسترسی به عنصر اصلی در DOM
              const rootElement = ref(null);
              const initialData = ref('در حال بارگذاری...');
  
              console.log('۱. کامپوننت در حال setup شدن است.');
  
              // onBeforeMount یک هوک واقعی است!
              onBeforeMount(() => {
                  console.log('۲. onBeforeMount اجرا شد: آماده برای اتصال به DOM.');
                  
                  // در این لحظه، DOM هنوز ساخته نشده و در دسترس نیست.
                  // اگر تلاش کنیم به عنصر دسترسی پیدا کنیم، null خواهد بود.
                  console.log('مقدار rootElement در beforeMount:', rootElement.value); // خروجی: null
  
                  // یک کار منطقی برای این مرحله:
                  // فرض کنید یک محاسبه یا تنظیم اولیه قبل از رندر نیاز داریم
                  initialData.value = 'اطلاعات اولیه تنظیم شد!';
              });
  
              onMounted(() => {
                  console.log('۳. onMounted اجرا شد: کامپوننت به DOM متصل شد.');
                  
                  // حالا کامپوننت به صفحه اضافه شده و می‌توانیم به عناصر آن دسترسی داشته باشیم.
                  console.log('مقدار rootElement در mounted:', rootElement.value); // خروجی: <div id="app">...</div>
                  
                  // می‌توانیم DOM را دستکاری کنیم
                  rootElement.value.style.backgroundColor = '#e0f2f1';
              });
  
              return {
                  rootElement,
                  initialData
              };
          },
          // با استفاده از ref به عنصر اصلی متصل می‌شویم
          template: 
              <div ref="rootElement">
                  <h1>وضعیت کامپوننت</h1>
                  <p>{{ initialData }}</p>
              </div>
         
      }).mount('#app');
  </script>
  
  </body>
  </html>

```


## Slot در Vue JS
 اسلات (Slot) در Vue.js 3 یک مکانیزم قدرتمند برای توزیع محتوا (Content Distribution) است. به زبان ساده، اسلات به شما اجازه می‌دهد تا در یک کامپوننت فرزند (Child Component)، فضایی را به عنوان "جایگاه" تعریف کنید که کامپوننت والد (Parent Component) بتواند محتوای دلخواه خود را در آن قرار دهد. این کار باعث می‌شود کامپوننت‌های شما بسیار انعطاف‌پذیر و قابل استفاده مجدد (reusable) شوند.

 تصور کنید می‌خواهیم یک کامپوننت برای ساخت "کارت" (Card) داشته باشیم. این کارت یک کادر ساده با کمی استایل است. ما می‌خواهیم محتوای داخل این کارت را هر بار که از آن استفاده می‌کنیم، خودمان مشخص کنیم.

اینجا مفهوم پدری و فرزندی این‌طور تعریف می‌شود:

فرزند (Child): کامپوننت Card.vue که فقط شکل و ظاهر کادر را تعریف می‌کند و یک "جای خالی" برای محتوا دارد.

والد (Parent): کامپوننتی که Card.vue را فراخوانی می‌کند و آن "جای خالی" را با متن، عکس یا هر چیز دیگری پر می‌کند.


### ۱. کامپوننت فرزند: Card.vue
این کامپوننت فقط یک <div> با استایل مشخص و یک تگ <slot> در داخل آن است. تگ <slot> مثل یک جای خالی عمل می‌کند که منتظر محتوای کامپوننت والد است
```vue
<template>
  <div class="card-wrapper">
    <slot></slot>
  </div>
</template>

<style scoped>
.card-wrapper {
  padding: 20px;
  margin: 15px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #f9f9f9;
  border: 1px solid #e0e0e0;
}
</style>

```

نکته کلیدی: تمام کاری که این کامپوننت انجام می‌دهد این است که یک کادر زیبا بسازد و بگوید: "من یک جای خالی در درونم دارم!.

### ۲. کامپوننت والد: App.vue
حالا در کامپوننت والد، ما از Card.vue استفاده می‌کنیم. هر چیزی که بین تگ‌های باز و بسته <Card> بنویسیم، به صورت خودکار به داخل همان <slot> در کامپوننت فرزند فرستاده می‌شود.

```vue

<template>
  <div id="app">
    <h1>استفاده از کامپوننت کارت</h1>

    <Card>
      <h2>این عنوان کارت اول است</h2>
      <p>این یک پاراگراف ساده است که در داخل کارت قرار گرفته.</p>
    </Card>

    <Card>
      <p>این کارت فقط یک متن کوتاه دارد.</p>
      <button>یک دکمه!</button>
    </Card>

    <Card>
      <img src="https://vuejs.org/images/logo.png" alt="Vue Logo" width="80">
      <p style="text-align: center;">کارت با لوگوی Vue</p>
    </Card>

  </div>
</template>

<script setup>
import Card from './components/Card.vue';
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 40px;
}
</style>
```
نتیجه چه می‌شود؟
والد (App.vue) سه بار کامپوننت Card را صدا می‌زند.

در هر بار فراخوانی، محتوای متفاوتی را بین <Card> و </Card> قرار می‌دهد.

فرزند (Card.vue) این محتوا را می‌گیرد و دقیقاً در جایی که تگ <slot> قرار دارد، نمایش می‌دهد.

این مثال نشان می‌دهد که شما یک کامپوننت Card با ظاهر ثابت دارید، اما به لطف اسلات، می‌توانید بی‌نهایت محتوای متفاوت را درون آن قرار دهید. این یعنی انعطاف‌پذیری و استفاده مجدد (Reusability) بالا.




یک فایل jsconfig.json خوب و استاندارد برای یک پروژه Vue.js، معمولاً سه بخش اصلی را شامل می‌شود:
## Jsconfig.json

#### compilerOptions

#### include

#### exclude

بخش‌های اصلی jsconfig.json
در ادامه، وظیفه هر بخش به همراه یک نمونه کامل توضیح داده شده است.

#### 1. compilerOptions (تنظیمات کامپایلر)
این بخش، قلب فایل کانفیگ شماست و به ویرایشگر کد می‌گوید که چگونه کد جاوااسکریپت شما را تحلیل و درک کند.

baseUrl: مسیر پایه‌ای را برای پیدا کردن فایل‌ها مشخص می‌کند. معمولاً روی . (پوشه ریشه پروژه) تنظیم می‌شود.

paths: این یک قابلیت بسیار کاربردی برای تعریف مسیرهای کوتاه و خوانا است. برای مثال، به جای نوشتن ../../components/Button.vue، می‌توانید از @/components/Button.vue استفاده کنید.

target و module: نسخه جاوااسکریپت و سیستم ماژول‌بندی پروژه شما را مشخص می‌کنند. برای پروژه‌های مدرن، esnext انتخاب خوبی است.

moduleResolution: نحوه پیدا کردن ماژول‌ها را تعیین می‌کند. برای پروژه‌های Vue که از npm استفاده می‌کنند، مقدار node صحیح است.

2. include (فایل‌های شامل شونده)
این بخش به ویرایشگر می‌گوید که دقیقاً کدام فایل‌ها و پوشه‌ها را باید به عنوان بخشی از پروژه شما در نظر بگیرد. این کار عملکرد ویرایشگر را به شدت بهبود می‌بخشد.

3. exclude (فایل‌های نادیده گرفته شده)
این بخش به ویرایشگر می‌گوید که کدام پوشه‌ها را باید کامل نادیده بگیرد. این کار برای جلوگیری از تحلیل پوشه‌های سنگین و غیرمرتبط مانند node_modules (تمام پکیج‌های نصب شده) و dist (فایل‌های خروجی پروژه) ضروری است.



# نمونه کامل و پیشنهادی Vue 2
این یک نمونه عالی و کامل برای یک پروژه Vue 2 است که می‌توانید مستقیماً از آن استفاده کنید:
```json
{
  // تنظیمات اصلی برای تحلیل کد
  "compilerOptions": {
    // مسیر پایه برای ایمپورت فایل‌ها (ریشه پروژه)
    "baseUrl": ".",

    // تعریف مسیرهای کوتاه و خوانا
    "paths": {
      "@/*": ["src/*"]
    },

    // نسخه جاوااسکریپت هدف
    "target": "esnext",

    // سیستم ماژول‌بندی پروژه
    "module": "esnext",
    
    // الگوریتم پیدا کردن ماژول‌ها
    "moduleResolution": "node"
  },

  // ✅ فقط این فایل‌ها را به عنوان بخشی از پروژه بشناس
  "include": [
    "src/**/*.js",
    "src/**/*.vue",
    "tests/**/*.js"
  ],

  // ❌ این پوشه‌ها را کامل نادیده بگیر
  "exclude": [
    "node_modules",
    "dist"
  ]
}
```

#### مهم‌ترین تفاوت این است که پروژه‌های Vue 3 معمولاً با ابزار Vite ساخته می‌شوند و استفاده از TypeScript در آنها بسیار رایج‌تر است.

#### نمونه jsconfig.json برای پروژه Vue 3 (جاوااسکریپت)
این یک نمونه عالی برای یک پروژه Vue 3 است که با Vite و جاوااسکریپت خالص (بدون تایپ‌اسکریپت) ساخته شده باشد:


```json

{
  "compilerOptions": {
    // تنظیم نسخه جاوااسکریپت مدرن که با Vue 3 و Vite سازگار است
    "target": "esnext",
    "module": "esnext",
    
    // الگوریتم استاندارد برای پیدا کردن ماژول‌ها
    "moduleResolution": "node",

    // مسیر پایه برای تعریف path های کوتاه
    "baseUrl": ".",
    
    // تعریف مسیر @ برای اشاره به پوشه src (بسیار رایج در پروژه‌های Vite)
    "paths": {
      "@/*": ["src/*"]
    },
    
    // اجازه می‌دهد تا با کتابخانه‌های مختلف جاوااسکریپت کار کنید
    "lib": ["esnext", "dom"],
    
    // اجازه می‌دهد تا فایل‌های JSON را مستقیماً import کنید
    "resolveJsonModule": true,

    // قابلیت همکاری بهتر بین ماژول‌های CommonJS و ES Modules
    "esModuleInterop": true
  },
  
  // فایل‌هایی که باید تحلیل شوند
  "include": [
    "src/**/*.js",
    "src/**/*.vue"
  ],

  // پوشه‌هایی که باید نادیده گرفته شوند
  "exclude": [
    "node_modules",
    "dist"
  ]
}
```
حتماً. وقتی یک پروژه Vue 3 را با پشتیبانی از تایپ‌اسکریپت ایجاد می‌کنید (مثلاً با ابزار رسمی npm create vue@latest)، یک فایل tsconfig.json به صورت خودکار برای شما ساخته می‌شود که بسیار کامل و بهینه است.

در ادامه یک نمونه استاندارد و کاملاً بهینه شده از این فایل برای یک پروژه Vue 3 + Vite + TypeScript را به همراه توضیحات کامل مشاهده می‌کنید.

نمونه کامل tsconfig.json برای Vue 3 با تایپ اسکریپت 
‍‍‍```json
{
  // تنظیمات اصلی کامپایلر تایپ‌اسکریپت
  "compilerOptions": {
    // نسخه جاوااسکریپت خروجی (esnext یعنی آخرین نسخه مدرن)
    "target": "ESNext",
    
    // اجازه می‌دهد تا از سینتکس مدرن جاوااسکریپت استفاده کنید
    "useDefineForClassFields": true,
    
    // سیستم ماژول‌بندی پروژه (سازگار با Vite و مرورگرهای مدرن)
    "module": "ESNext",
    
    // نحوه پیدا کردن ماژول‌ها (استاندارد برای پروژه‌های Node.js)
    "moduleResolution": "Node",
    
    // اعمال بررسی‌های دقیق‌تر برای null و undefined
    "strict": true,
    
    // قابلیت بررسی نوع در فایل‌های جاوااسکریپت (برای پروژه‌های ترکیبی)
    "allowJs": true,
    
    // برای پشتیبانی از ابزارهای توسعه‌دهنده Vue در مرورگر
    "sourceMap": true,
    
    // مسیر پایه برای تعریف path های کوتاه
    "baseUrl": ".",
    
    // تعریف مسیرهای کوتاه (alias)
    "paths": {
      "@/*": ["src/*"]
    },
    
    // کتابخانه‌هایی که تایپ‌اسکریپت باید بشناسد
    "lib": ["ESNext", "DOM"],
    
    // این گزینه برای Vite و ابزارهای مشابه ضروری است تا فایل‌ها به صورت جداگانه کامپایل شوند
    "isolatedModules": true,

    // قابلیت همکاری بهتر بین ماژول‌های CommonJS و ES Modules
    "esModuleInterop": true,
    
    // انواع تایپ‌هایی که باید به صورت گلوبال در دسترس باشند (مثلاً برای Vite)
    "types": ["vite/client"]
  },

  // فایل‌ها و پوشه‌هایی که باید توسط تایپ‌اسکریپت تحلیل شوند
  "include": ["src/**/*.ts", "src/**/*.d.ts", "src/**/*.tsx", "src/**/*.vue"],
  
  // ارجاع به فایل کانفیگ دیگر (مخصوص تنظیمات Vite)
  "references": [{ "path": "./tsconfig.node.json" }]
}
```

در مسیردهی ها @ به پوشه src اشاره دارد
## Vue Router 🚦
<div dir="rtl">
  
Vue Router کتابخانه رسمی Vue.js برای مسیریابی (Routing) در اپلیکیشن‌های تک‌صفحه‌ای (Single Page Applications - SPA) است.

</div>


به زبان ساده: وقتی در یک سایت روی لینک‌های مختلف (مثلاً "درباره ما" یا "تماس با ما") کلیک می‌کنید و صفحه بدون رفرش شدن کامل، فقط محتوای اصلی‌اش عوض می‌شود، این کار را Router انجام می‌دهد. او URL مرورگر را به یک کامپوننت خاص در Vue متصل می‌کند.

چه زمانی استفاده می‌شود؟ هر وقت اپلیکیشن شما بیشتر از یک "صفحه" یا "نما" (View) داشته باشد.

اجزای کلیدی:

`<router-link to="/about">:` جایگزین تگ `<a>` برای ساختن لینک‌ها.

`<router-view>:` کامپوننتی که مانند یک جایگاه عمل کرده و کامپوننت مربوط به URL فعلی را نمایش می‌دهد.


```javascript
// 1. تعریف کامپوننت‌ها
const Home = { template: '<div>صفحه اصلی</div>' }
const About = { template: '<div>درباره ما</div>' }

// 2. تعریف مسیرها (Routes)
const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About },
]

// 3. ساختن نمونه Router
const router = VueRouter.createRouter({
  history: VueRouter.createWebHistory(),
  routes,
})

```

در کامپوننت اصلی (App.vue):
```html
<header>
  <router-link to="/">خانه</router-link> |
  <router-link to="/about">درباره ما</router-link>
</header>
<main>
  <router-view></router-view>
</main>

```

## State (وضعیت) 🧠
State به زبان ساده همان داده‌های (data) برنامه شماست که در طول زمان تغییر می‌کنند. هر چیزی که وضعیت فعلی اپلیکیشن شما را مشخص می‌کند، State محسوب می‌شود.

مثال:

آیا کاربر وارد شده است یا نه (isLoggedIn: true).

لیست آیتم‌ها در سبد خرید (cartItems: [...]).

نام کاربری که در پروفایل نمایش داده می‌شود (username: 'ali').

مشکل: وقتی برنامه بزرگ می‌شود، مدیریت این داده‌ها و به اشتراک گذاشتن آن‌ها بین کامپوننت‌های مختلف پیچیده می‌شود. برای حل این مشکل از "Store" استفاده می‌کنیم.






## Store و Pinia 🍍
Store (انبار) یک الگوی طراحی است که در آن تمام State اشتراکی برنامه در یک مکان مرکزی نگهداری می‌شود. Pinia کتابخانه رسمی و مدرن Vue.js برای پیاده‌سازی این الگو است. (Pinia جایگزین Vuex شده است).

به زبان ساده: Pinia مثل یک انبار مرکزی برای داده‌های مهم برنامه شماست. هر کامپوننتی که به داده‌ای نیاز داشته باشد، آن را از این انبار درخواست می‌کند و اگر داده‌ای در انبار تغییر کند، تمام کامپوننت‌هایی که از آن استفاده می‌کنند، به‌صورت خودکار آپدیت می‌شوند.

چه زمانی استفاده می‌شود؟ وقتی نیاز دارید یک State را بین چندین کامپوننت (که شاید رابطه پدر-فرزندی مستقیمی ندارند) به اشتراک بگذارید. مثلا وضعیت لاگین کاربر یا محتوای سبد خرید.

اجزای کلیدی Pinia:


`state:` داده‌های اصلی (مثل data در کامپوننت).

`getters:` داده‌های مشتق‌شده (مثل computed properties).

`actions:` متدهایی برای تغییر state (مثل methods در کامپوننت).


مثال یک Store ساده در Pinia:
```JavaScript
// stores/counter.js
import { defineStore } from 'pinia'

export const useCounterStore = defineStore('counter', {
  state: () => ({
    count: 0,
    userName: 'Guest'
  }),
  getters: {
    doubleCount: (state) => state.count * 2,
  },
  actions: {
    increment() {
      this.count++
    },
  },
})
```

نحوه استفاده در یک کامپوننت:

```vue
<template>
  <div>
    <p>تعداد: {{ counter.count }}</p>
    <button @click="counter.increment()">افزایش</button>
  </div>
</template>

<script setup>
import { useCounterStore } from '@/stores/counter'

const counter = useCounterStore()
</script>

```
## Local Storage 💾
Local Storage یک ویژگی مرورگر است، نه بخشی از Vue.js. این قابلیت به شما اجازه می‌دهد تا داده‌ها را به‌صورت متن (key-value) در مرورگر کاربر ذخیره کنید.

مهم‌ترین ویژگی: داده‌های ذخیره شده در Local Storage حتی پس از بستن و باز کردن مجدد مرورگر یا رفرش کردن صفحه، باقی می‌مانند.

تفاوت کلیدی با State/Pinia:

State در Pinia با رفرش شدن صفحه از بین می‌رود و به مقدار اولیه‌اش برمی‌گردد.

داده در Local Storage ماندگار است.

چه زمانی استفاده می‌شود؟ معمولاً برای ماندگار کردن (persisting) وضعیت برنامه. برای مثال، می‌توانید اطلاعات سبد خرید کاربر را در Local Storage ذخیره کنید تا اگر کاربر صفحه را بست و دوباره برگشت، سبد خریدش خالی نشود.

```javascript
// ذخیره کردن نام کاربر در Local Storage
localStorage.setItem('username', 'Reza');

// خواندن نام کاربر از Local Storage
const savedUsername = localStorage.getItem('username'); // "Reza"

// ذخیره کردن یک آبجکت (باید به رشته JSON تبدیل شود)
const cart = { items: ['book', 'pen'], total: 25000 };
localStorage.setItem('shoppingCart', JSON.stringify(cart));

// خواندن آبجکت (باید از رشته JSON به آبجکت پارس شود)
const savedCart = JSON.parse(localStorage.getItem('shoppingCart'));

```
## مثالی دیگر :
#### یک مثال کامل و کاربردی از یک اپلیکیشن لیست کارها (To-Do List)

کاری که این اپلیکیشن انجام می‌دهد:
-دارای دو صفحه است: صفحه "لیست کارها" و صفحه "درباره ما" (نیازمند Router).

-شما می‌توانید کارهای جدید اضافه کنید و وضعیت انجام شدن آن‌ها را تغییر دهید (نیازمند State که با Pinia مدیریت می‌شود).

-لیست کارها حتی پس از بستن یا رفرش کردن صفحه هم باقی می‌ماند (نیازمند Local Storage برای ذخیره‌سازی).

##### ساختار فایل‌ها
```less

/src
├── components/
│   └── TodoItem.vue        # کامپوننت برای نمایش یک آیتم در لیست
├── views/
│   ├── HomeView.vue        # صفحه اصلی که لیست کارها را نشان می‌دهد
│   └── AboutView.vue       # صفحه درباره ما
├── stores/
│   └── todoStore.js        # استور Pinia برای مدیریت کارها
├── router/
│   └── index.js            # فایل تنظیمات Vue Router
├── App.vue                 # کامپوننت اصلی و ریشه برنامه
└── main.js                 # نقطه ورود برنامه
```
#### ۱. راه‌اندازی Pinia Store (با Local Storage)
این فایل، مغز اپلیکیشن ماست. وضعیت (State) لیست کارها را نگه می‌دارد و هر بار که تغییری ایجاد می‌شود، آن را در Local Storage ذخیره می‌کند.

فایل: `src/stores/todoStore.js`

```javascript

import { defineStore } from 'pinia'
import { ref, watch } from 'vue'

export const useTodoStore = defineStore('todo', () => {
  // ۱. State: خواندن لیست کارها از Local Storage یا استفاده از آرایه خالی
  const todos = ref(JSON.parse(localStorage.getItem('todos')) || [])

  // ۲. Action: افزودن یک کار جدید
  function addTodo(text) {
    if (!text) return
    todos.value.unshift({ id: Date.now(), text, completed: false })
  }

  // ۳. Action: تغییر وضعیت انجام شدن یک کار
  function toggleTodo(id) {
    const todo = todos.value.find((t) => t.id === id)
    if (todo) {
      todo.completed = !todo.completed
    }
  }

  // ۴. اتصال به Local Storage: هر زمان لیست کارها تغییر کرد، آن را در Local Storage ذخیره کن
  watch(
    todos,
    (newTodos) => {
      localStorage.setItem('todos', JSON.stringify(newTodos))
    },
    { deep: true } // برای اینکه تغییرات درون آبجکت‌ها را هم تشخیص دهد
  )

  return { todos, addTodo, toggleTodo }
})

```
#### ۲. راه‌اندازی Vue Router
این فایل مسیرها و کامپوننت‌های متناظر با آن‌ها را تعریف می‌کند.

فایل: `src/router/index.js`

```javascript
import { createRouter, createWebHistory } from 'vue-router'
import HomeView from '../views/HomeView.vue'
import AboutView from '../views/AboutView.vue'

const routes = [
  {
    path: '/',
    name: 'Home',
    component: HomeView,
  },
  {
    path: '/about',
    name: 'About',
    component: AboutView,
  },
]

const router = createRouter({
  history: createWebHistory(),
  routes,
})

export default router

```


#### ۳. ساخت View ها (صفحات)
این کامپوننت‌ها، صفحاتی هستند که Router آن‌ها را نمایش می‌دهد.

فایل: `src/views/HomeView.vue` (صفحه اصلی)

```vue
<template>
  <div class="home-view">
    <h1>لیست کارهای من</h1>
    <input
      type="text"
      v-model="newTodoText"
      @keyup.enter="add"
      placeholder="یک کار جدید اضافه کنید..."
    />
    <button @click="add">افزودن</button>

    <div class="todo-list">
      <TodoItem
        v-for="todo in todoStore.todos"
        :key="todo.id"
        :todo="todo"
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useTodoStore } from '@/stores/todoStore'
import TodoItem from '@/components/TodoItem.vue'

const newTodoText = ref('')
const todoStore = useTodoStore() // استفاده از استور

function add() {
  todoStore.addTodo(newTodoText.value)
  newTodoText.value = '' // خالی کردن اینپوت
}
</script>

<style scoped>
.home-view { max-width: 500px; margin: 0 auto; }
input { width: 70%; padding: 8px; }
button { padding: 8px; }
.todo-list { margin-top: 20px; }
</style>

```

 فایل: ` src/views/AboutView.vue ` (صفحه درباره ما)
 
 ```vue
<template>
  <div class="about">
    <h1>درباره این پروژه</h1>
    <p>این یک مثال کامل برای نمایش نحوه کارکرد Vue Router، Pinia و Local Storage است.</p>
  </div>
</template>
```

#### ۴. ساخت کامپوننت آیتم لیست
این کامپوننت کوچک فقط یک آیتم از لیست کارها را نمایش می‌دهد.

فایل: `src/components/TodoItem.vue`
``` vue


<template>
  <div class="todo-item" :class="{ completed: todo.completed }">
    <p>{{ todo.text }}</p>
    <button @click="todoStore.toggleTodo(todo.id)">
      {{ todo.completed ? 'لغو' : 'انجام شد' }}
    </button>
  </div>
</template>

<script setup>
import { useTodoStore } from '@/stores/todoStore'

defineProps({
  todo: Object,
})

const todoStore = useTodoStore()
</script>

<style scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  border-bottom: 1px solid #eee;
}
.todo-item.completed p {
  text-decoration: line-through;
  color: #aaa;
}
</style>

```
#### ۵. کامپوننت اصلی و نقطه ورود
فایل: `src/App.vue` (کامپوننت ریشه)
این کامپوننت، منوی ناوبری و جایگاه نمایش صفحات (`<router-view>`) را در خود دارد.

```vue


<template>
  <div id="app">
    <nav>
      <router-link to="/">لیست کارها</router-link> |
      <router-link to="/about">درباره ما</router-link>
    </nav>
    <main>
      <router-view />
    </main>
  </div>
</template>

<style>
/* استایل‌های عمومی */
#app { text-align: center; color: #2c3e50; }
nav { padding: 30px; }
nav a { font-weight: bold; color: #2c3e50; }
nav a.router-link-exact-active { color: #42b983; }
</style>

```
فایل: `src/main.js` (نقطه ورود)
این فایل، برنامه Vue را می‌سازد و Pinia و Router را به آن متصل می‌کند.

```javascript
import { createApp } from 'vue'
import { createPinia } from 'pinia'
import App from './App.vue'
import router from './router' // ایمپورت کردن روتر

const app = createApp(App)

app.use(createPinia()) // اتصال Pinia
app.use(router)        // اتصال Router

app.mount('#app')

```
## Axios
<div dir='rtl'>
یک کتابخانه جاوا اسکریپت است که برای ارسال درخواست‌های HTTP استفاده می‌شود. به دلیل سادگی و قدرت بالا، به طور گسترده‌ای در کنار فریمورک‌هایی مانند Vue، React و Angular به کار می‌رود.

کاربرد اصلی آن، برقراری ارتباط بین اپلیکیشن شما (front-end) و سرور (back-end) برای دریافت یا ارسال داده است.


تصور کنید اپلیکیشن شما یک مشتری در رستوران است و سرور، آشپزخانه است. Axios نقش همان پیشخدمت (Waiter) 🤵 را بازی می‌کند.

شما (اپلیکیشن) به پیشخدمت (Axios) می‌گویید که چه چیزی می‌خواهید (مثلاً "لیست کاربران را به من بده"). پیشخدمت درخواست شما را به آشپزخانه (سرور) می‌برد، منتظر آماده شدن سفارش می‌ماند و در نهایت، غذا (داده‌ها) را برای شما می‌آورد.

Axios این فرآیند ارسال درخواست (Request) و دریافت پاسخ (Response) را بسیار ساده و قابل مدیریت می‌کند. این کتابخانه مبتنی بر Promise است، که به شما اجازه می‌دهد کدهای غیرهمزمان (asynchronous) را به شیوه‌ای تمیز بنویسید.

</div>

#### کاربردها و ویژگی‌های اصلی
دریافت داده از سرور (متد GET):
بیشترین کاربرد Axios برای گرفتن اطلاعات از یک API است. مثلاً دریافت لیست محصولات، اطلاعات یک کاربر خاص یا مقالات یک وبلاگ.
```javascript
axios.get('https://api.example.com/products')
  .then(response => {
    console.log(response.data); // لیست محصولات
  })
  .catch(error => {
    console.error('خطایی رخ داد!', error);
  });

```

#### ارسال داده به سرور (`متدهای POST, PUT, DELETE`):
برای ساختن یک موجودیت جدید (مثلاً ثبت‌نام کاربر با POST)، به‌روزرسانی اطلاعات (ویرایش پروفایل با PUT) یا حذف داده (حذف یک آیتم با DELETE).
```javascript

const newUser = { name: 'Ali', email: 'ali@example.com' };

axios.post('https://api.example.com/users', newUser)
  .then(response => {
    console.log('کاربر با موفقیت ساخته شد:', response.data);
  });

```

#### رهگیرها (Interceptors): ✅
این یکی از قدرتمندترین ویژگی‌های Axios است. رهگیرها به شما اجازه می‌دهند کد خود را قبل از ارسال یک درخواست یا قبل از دریافت یک پاسخ اجرا کنید. کاربرد رایج آن، اضافه کردن خودکار توکن احراز هویت (Authentication Token) به هدر تمام درخواست‌ها است.

مدیریت خطاها:
به راحتی می‌توانید خطاهای شبکه یا خطاهایی که از سمت سرور می‌آیند (مثل خطای 404 Not Found) را مدیریت کنید.


آیا فقط برای Vue است؟
خیر. Axios یک کتابخانه مستقل است و به هیچ فریمورکی وابسته نیست. اما چون تقریباً تمام اپلیکیشن‌های Vue برای دریافت داده‌های داینامیک نیاز به برقراری ارتباط با یک سرور دارند، Axios به عنوان یک "همکار عالی" برای Vue شناخته می‌شود. نصب و استفاده از آن در پروژه‌های Vue بسیار ساده است.

مثال استفاده در یک کامپوننت Vue 3:

```vue
<template>
  <div>
    <h1>لیست پست‌ها</h1>
    <ul>
      <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios'; // ایمپورت کردن اکسوس

const posts = ref([]);

// onMounted یک هوک است که بعد از رندر شدن کامپوننت اجرا می‌شود
onMounted(async () => {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
    posts.value = response.data; // ذخیره داده‌های دریافتی در state
  } catch (error) {
    console.error('خطا در دریافت پست‌ها:', error);
  }
});
</script>
```

<div dir="ltr">

Zod یک کتابخانه اعتبارسنجی اسکما (schema validation) است که با اولویت TypeScript ساخته شده (TypeScript-first).

به زبان ساده، Zod به شما اجازه می‌دهد تا یک "بلوپرینت" یا "الگو" (که به آن اسکما می‌گویند) برای داده‌های خود تعریف کنید و سپس بررسی کنید که آیا داده‌های واقعی با آن الگو مطابقت دارند یا نه. ویژگی اصلی آن این است که به طور خودکار از روی اسکما، تایپ‌های TypeScript را برای شما ایجاد می‌کند.

#### Zod چیست؟ 🛡️
Zod مانند یک مسئول کنترل ورود یا نگهبان (Bouncer) برای داده‌های شما عمل می‌کند.

وقتی داده‌ای از یک منبع غیرقابل اعتماد (مانند یک API خارجی یا ورودی کاربر) وارد اپلیکیشن شما می‌شود، TypeScript به تنهایی نمی‌تواند در زمان اجرا (runtime) از صحت ساختار آن مطمئن شود. اینجا Zod وارد می‌شود. شما یک اسکما تعریف می‌کنید که می‌گوید: "من انتظار دارم داده ورودی یک آبجکت با یک id از نوع عددی و یک name از نوع رشته باشد."

سپس داده واقعی را به Zod می‌دهید. Zod آن را با الگو مقایسه می‌کند:

اگر مطابقت داشت: به داده اجازه ورود می‌دهد و شما با خیال راحت از آن استفاده می‌کنید.

اگر مغایرت داشت: یک خطا پرتاب می‌کند و جلوی ورود داده نامعتبر را می‌گیرد.

ویژگی کلیدی: شما فقط یک بار اسکما را تعریف می‌کنید و Zod به صورت خودکار تایپ TypeScript مربوط به آن را برای شما می‌سازد (z.infer). این کار از دوباره‌کاری جلوگیری کرده و تضمین می‌کند که اعتبارسنجی و تایپ‌های شما همیشه با هم هماهنگ هستند.

#### چرا و کجا از Zod استفاده می‌شود؟ 🔍
Zod پلی بین اعتبارسنجی در زمان اجرا و امنیت تایپ در زمان توسعه است. کاربردهای اصلی آن عبارتند از:

اعتبارسنجی پاسخ‌های API: این رایج‌ترین کاربرد است. وقتی با Axios داده‌ای از سرور می‌گیرید، هیچ تضمینی وجود ندارد که سرور دقیقاً همان ساختاری را که شما در تایپ‌های TypeScript خود تعریف کرده‌اید، بفرستد. Zod این پاسخ را اعتبارسنجی می‌کند تا مطمئن شوید داده‌ها ایمن و معتبر هستند.

اعتبارسنجی فرم‌های ورودی: قبل از ارسال اطلاعات فرم (مثلاً فرم ثبت‌نام) به سرور، می‌توانید با Zod مطمئن شوید که کاربر تمام فیلدها را با فرمت صحیح (مثلاً ایمیل معتبر، پسورد با طول کافی) پر کرده است.

ایجاد تایپ از روی اسکما: به جای تعریف دستی یک interface یا type در TypeScript و سپس نوشتن یک تابع اعتبارسنجی جداگانه، با Zod هر دو کار را همزمان انجام می‌دهید.

#### مثال عملی با Axios و Vue
در این مثال، ما با Axios اطلاعات یک کاربر را از یک API می‌گیریم و با Zod آن را اعتبارسنجی می‌کنیم.

</div>

```vue
<template>
  <div>
    <div v-if="error">خطا: {{ error }}</div>
    <div v-else-if="user">
      <h1>{{ user.name }}</h1>
      <p>ایمیل: {{ user.email }}</p>
      <p>وب‌سایت: {{ user.website }}</p>
    </div>
    <div v-else>در حال بارگذاری...</div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';
import { z } from 'zod'; // ۱. ایمپورت کردن Zod

// ۲. تعریف اسکما (الگو) برای داده کاربر
const UserSchema = z.object({
  id: z.number(),
  name: z.string(),
  email: z.string().email({ message: "ایمیل نامعتبر است" }),
  website: z.string().url().optional(), // این فیلد اختیاری است
});

// ۳. استخراج خودکار تایپ TypeScript از روی اسکما
// دیگر نیازی به نوشتن دستی interface User نیست!
const user = ref(null);
const error = ref(null);

onMounted(async () => {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/users/1');
    
    // ۴. اعتبارسنجی داده دریافتی با اسکما
    // اگر داده معتبر نباشد، .parse() یک خطا پرتاب می‌کند
    const validatedUser = UserSchema.parse(response.data);
    
    // حالا با خیال راحت از داده معتبر و تایپ-سیف استفاده می‌کنیم
    user.value = validatedUser;
    
  } catch (e) {
    if (e instanceof z.ZodError) {
      // اگر خطا از سمت Zod باشد (داده نامعتبر)
      error.value = e.errors[0].message; // نمایش اولین پیام خطا
    } else {
      // خطاهای دیگر (مثلاً خطای شبکه)
      error.value = 'امکان دریافت اطلاعات وجود نداشت.';
    }
  }
});
</script>

```

در این مثال، Zod تضمین می‌کند که داده‌ای که از API می‌آید، قبل از اینکه در اپلیکیشن شما استفاده شود، کاملاً معتبر و مطابق انتظار شماست.
