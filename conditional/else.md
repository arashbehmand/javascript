# Else

محتویات داخل عبارت `else` در حالتی اجرا می‌شوند که شرط if درست نبوده باشد. برای مثال این امکان در صورتی که بخواهید موردی خاص را استثنا قرار دهید و برای بقیه کار عادی را انجام بدهید سودمند خواهد بود:

```javascript
var umbrellaMandatory;

if(country === 'England'){
    umbrellaMandatory = true;
} else {
    umbrellaMandatory = false;
}
```

عبارت `else` می‌تواند به یک عبارت `if` دیگر متصل شود تا سلسله‌ای از شروط بررسی شوند. بیایید مثال مربوط به بخش قبل را بازنویسی کنیم:

```javascript
if(country === 'England') {
    ...
} else if(country === 'France') {
    ...
} else if(country === 'Germany') {
    ...
}
```


{% exercise %}
مقدار متغییر `name` را جوری تغییر دهید تا عبارت مربوط به `else` اجرا شود.
{% initial %}
var name =

if (name === "John") {

} else if (name === "Aaron") {
    // Valid this condition
}
{% solution %}
var name = "Aaron";

if (name === "John") {

} else if (name === "Aaron") {
    // Valid this condition
}
{% validation %}
assert(name === "Aaron");
{% endexercise %}
