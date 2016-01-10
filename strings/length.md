# طول

در جاوااسکریپت اطلاع از اینکه چند نویسه در یک رشته قرار دارند به سادگی توسط ویژگی[^1] `.length` انجام می‌شود.

```js
// کافیست از ویژگی .length استفاده کنید
var size = 'Our lovely string'.length;

```

**توجه:** رشته‌ها نمی‌توانند از هم کم شوند، در هم ضرب شوند یا تقسیم شوند.

{% exercise %}
در متغیری به اسم `size` طول رشته‌ای به نام `str` را ذخیره کنید.
{% initial %}
var str = "Hello World";

var size =
{% solution %}
var str = "Hello World";

var size = str.length;
{% validation %}
assert(size === str.length);
{% endexercise %}

[^1]: Property