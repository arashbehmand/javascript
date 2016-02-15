# حلقه For

ساده‌ترین شکلی یک حلقه عبارت `for` است. نحوه نوشتن آن به شکل زیر است:

```javascript
for(راه‌اندازی اولیه; شرط پایان; تغییر){
    //کاری که باید انجام شود
}
```

برای مثال برای 10 بار اجرای یک دستور توسط حلقه `for` می‌نویسیم:

```
for(var i = 0; i < 10; i = i + 1){
    // این کد را ده بار اجرا کن
}
```


{% exercise %}
توسط یک حلقه for یک متغییر از جنس رشته با نام `message` درست کنید که مقدار آن حاصل از چسباندن اعداد صحیح از ۱ تا ۱۰۰ باشد.
{% initial %}
var message = "";
{% solution %}
var message = "";

for(var i = 0; i < 100; i++){
    message = message + (i+1);
}
{% validation %}
var message2 = ""

for(var i = 0; i < 100; i++){
    message2 = message2 + (i+1);
}
assert(message === message2);
{% endexercise %}
