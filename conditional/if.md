# شرط If

ساده ترین عبارت شرطی، گذاره if است که نحوه نوشتن آن به شکل `if(شرط){ کاری را انجام بده … }` است. برای اینکه عبارات داخل آکولاد اجرا شوند شرط داخل پرانتز باید حتما صحیح باشد. برای مثال می‌توانید مقدار رشته‌ای را در شرط خود بررسی کنید و مقدار رشته دیگری را متناسب با آن تعیین کنید:

```javascript
var country = 'France';
var weather;
var food;
var currency;

if(country === 'England') {
    weather = 'horrible';
    food = 'filling';
    currency = 'pound sterling';
}

if(country === 'France') {
    weather = 'nice';
    food = 'stunning, but hardly ever vegetarian';
    currency = 'funny, small and colourful';
}

if(country === 'Germany') {
    weather = 'average';
    food = 'wurst thing ever';
    currency = 'funny, small and colourful';
}

var message = 'this is ' + country + ', the weather is ' +
            weather + ', the food is ' + food + ' and the ' +
            'currency is ' + currency;
```

**توجه:** شروط ممکن است تو در تو باشند.

{% exercise %}

مقدار متغییر `name` را جوری تعیین کنید که شرط زیر صادق باشد.
{% initial %}
var name =

if (name === "John") {

}
{% solution %}
var name = "John";

if (name === "John") {

}
{% validation %}
assert(name === "John");
{% endexercise %}
