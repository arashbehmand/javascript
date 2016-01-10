# حلقه While

حلقه `while` مادامی که ظرطی برقرار باشد، مجموعه‌ای از دستورات را انجام می‌دهد.

```javascript
while(شرط){
    // مادامی که شرط برقرار است این کار را انجام بده
}
```

برای مثال حلقه زیر مادامی که مقدار متغییر i کمتر از 5 باشد، اجرا خواهد شد:

```javascript
var i = 0, x = "";
while (i < 5) {
    x = x + "The number is " + i;
    i++;
}
```

**توجه**: دقت داشته باشید که اگر شرطتان همیشه درست باشد دچار حلقه بی‌نهایت خواهید شد.


{% exercise %}
توسط یک حلقه while متغییری به اسم `message` بسازید و مادامی که طول آن (`message.length`) کوچکتر از ۱۰۰ است، اعداد صحیح (0, 1, 2, ...) را به انتهای آن بچسبانید.
{% initial %}
var message = "";
{% solution %}
var message = "";
var i = 0;

while (message.length < 100) {
    message = message + i;
    i = i + 1;
}
{% validation %}
var message2 = "";
var i2 = 0;

while (message2.length < 100) {
    message2 = message2 + i2;
    i2 = i2 + 1;
}
assert(message === message2);
{% endexercise %}
