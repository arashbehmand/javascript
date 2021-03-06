# خواص

خواص اشیا به شکل ازواج `propertyName`: `propertyValue` هستند، به نحوی که **نام خاصیت فقط می‌تواند رشته باشد**. اگر هم رشته نباشد به رشته تبدیل می‌شود. شما می‌توانید خواص را وقتی **شی را می‌سازید** و **یا بعدا** مشخص کنید. خواص می‌توانند صفر عدد یا بیشتر باشند، که با کاراکتر ویرگول از هم جدا می‌شوند.
```js
var language = {
    name: 'JavaScript',
    isSupportedByBrowsers: true,
    createdIn: 1995,
    author:{
        firstName: 'Brendan',
        lastName: 'Eich'
    },
 // بله! می‌توان شی‌ای را به عنوان خاصیت یک شی دیگر داشت
    getAuthorFullName: function(){
        return this.author.firstName + " " + this.author.lastName;    
    }
 // بله توابع نیز می‌توانند مقدار یک خاصیت باشند.
};

```
در قطعه کد زیر می‌توانید نحوه **گرفتن** مقدار یک خاصیت را ببینید..
```js
var variable = language.name;
 // متغییر فوق مقدارش برابر با "JavaScript" خواهد شد.
    variable = language['name'];
 // این شیوه نیز دقیقا معادل کد بالاست، با این تفاوت که کد شما کمتر خوانایی خواهد داشت.
    variable = language.newProperty; 
 // با توجه به اینکه خاصیت فوق تعریف نشده، مقدار متغییر undefined خواهد شد.
```

کد زیر نجوه **اضافه کردن** خاصیت جدید یا **تغییر دادن** خاصیتی موجود را نشان می‌دهد.
```js
language.newProperty = 'new value';
 // حالا شی ما خاصیت جدید فوق را خواهد داشت. البته اگر قبلا آن را می‌داشت، فقط مقدارش عوض می‌شد.
language['newProperty'] = 'changed value';
 // باز هم مثل کمی بالاتر، این کد هم می‌تواند برای دسترسی به مقادیر خواص یک شی استفاده شود، ولی روش نقطه (بالا) توصیه می‌شود.
```
