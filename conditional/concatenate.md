# ترکیب شروط

شما می‌توانید شروط مختلف را به وسیله منطق «و» یا «یا» با یکدیگر ترکیب کنید تا بتوانید بررسی کنید که هر دو شرط یا حداقل یکی از شروط برقرار بوده.

در جاوااسکریپیت «یا» به شکل `||` و «و» به شکل `&&` نوشته می‌شوند.

فرض کنیم شما می‌خواهید بررسی کنید که x مابین 10 و -20 باشد، شما می‌توانید از شرط زیر استفاده کنید:

```
if(x > 10 && x < 20) {
    ...
}
```

اگر بخواهید مطمئن شوید که country یا "England" است و یا "Germany" است، می‌توانید بنویسید:

```
if(country === 'England' || country === 'Germany') {
    ...
}
```

**توجه**: مشابه با عملیات ریاضی روی متغییر‌ها، عملگرها هم می‌توانند توسط پرانتز گروه‌بندی و اولویت‌دهی شوند. برای مثال: ```if ( (name === 'John' || name === 'Jennifer') && country === 'France')```.

{% exercise %}
دو شرط خواسته شده را طوری پرکنید که `primaryCategory` مساوی با `"E/J"` شود، اگر و فقط اگر name برابر با `"John"` باشد و country برابر با `"England"`، و همچنین`secondaryCategory` برابر با `"E|J"` شود، اگر و فقط اگر name برابر با `"John"` باشد یا country برابر با `"England"` باشد.
{% initial %}
var name = "John";
var country = "England";
var primaryCategory, secondaryCategory;

if ( /* اینجا را پرکنید */ ) {
    primaryCategory = "E/J";
}
if ( /* اینجا را پر کنید */ ) {
    secondaryCategory = "E|J";
}
{% solution %}
var name = "John";
var country = "England";
var primaryCategory, secondaryCategory;

if (name === "John" && country === "England") {
    primaryCategory = "E/J";
}
if (name === "John" || country === "England") {
    secondaryCategory = "E|J";
}
{% validation %}
assert(primaryCategory === "E/J" && secondaryCategory === "E|J");
{% endexercise %}
