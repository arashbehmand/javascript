# حاشیه‌نویسی[^1]

حاشیه‌نویسی یا توضیح‌ها عباراتی هستند که توسط مفسر اجرا نمی‌شوند، حاشیه‌نویسی‌ها برای نوشتن یادداشت برای سایر برنامه‌نویسان یا برای توضیحی کوتاه راجع به عملکرد کد استفاده می‌شوند، تا درک آن را برای سایرین ساده‌تر کنند.

در جاوااسکریپت، دو روش برای حاشیه‌نویسی وجود دارد:

* هر چیزی بعد از `//` نوشته شود.:

```javascript
// This is a comment, it will be ignored by the interpreter
var a = "this is a variable defined in a statement"; // This is another comment
```

* بخش‌هایی از کد که بین `/*` و `*/` محصور باشند. این روش برای نوشتن حاشیه‌های چند خطی استفاده می‌شود:

```javascript
/*
This is a multi-line comment,
it will be ignored by the interpreter
*/
var a = "this is a variable defined in a statement";
```


{% exercise %}
نوشته زیر را تبدیل به حاشیه‌نویسی کنید
{%initial%}
Mark me as a comment
or I'll throw an error
{% solution %}
/*
Mark me as a comment
or I'll throw an error
*/
{% validation %}
assert(true);
{% endexercise %}

[^1]: Comment