# اندیس‌ها

وقتی یک آرایه داریم به چه شکل می‌شود به المان‌ خاصی از آن دسترسی داشت؟ اینجا جاییست که اندیس‌ها اهمیت پیدا می‌کنند. **اندیس** ارجاع دهنده به مکان خاصی از آرایه است. اندیس‌ها اصولا یکی یکی زیاد می‌شوند، اما لازم به ذکر است که اولین اندیس یک آرایه در جاوااسکریپت به مانند بسیاری از زبان‌های برنامه‌نویسی 0 است. از براکت‌ها (`[]`) برای ارجاع به اندیس مشخصی از یک آرایه استفاده می‌شود.

```javascript
// این آرایه‌ای از رشته‌هاست
var fruits = ["apple", "banana", "pineapple", "strawberry"];

// مقدار متغیر banana را مساوی مقدار دومین المان آرایه
// میوه‌ها قرار می‌دهیم. به یاد داشته باشید که اندیس‌ها 
// از 0 شروع می‌شوند، بنابراین ۱ بیانگر دومین المان است.
var banana = fruits[1]; // نتیجه: banana = "banana"
```

{% exercise %}
متغیر‌هایی با کمک اندیس‌های مختلف آرایه زیر بسازید.
{% initial %}
var cars = ["Mazda", "Honda", "Chevy", "Ford"]
var honda =
var ford =
var chevy =
var mazda =
{% solution %}
var cars = ["Mazda", "Honda", "Chevy", "Ford"]
var honda = cars[1];
var ford = cars[3];
var chevy = cars[2];
var mazda = cars[0];
{% validation %}
assert(honda === "Honda");
assert(ford === "Ford");
assert(chevy === "Chevy");
assert(mazda === "Mazda");
{% endexercise %}
