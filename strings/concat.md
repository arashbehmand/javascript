# چسباندن

چسباندن به معنای قرار دادن دو یا چند رشته در کنار هم و ساختن یک رشته طولانی‌تر است که حاوی داده ترکیب شده رشته‌های اولیه باشد. این کار در جاوااسکریپت توسط عملگر `+` انجام می‌شود.

```js
var bigStr = 'Hi ' + 'JS strings are nice ' + 'and ' + 'easy to add';
```

{% exercise %}
قسمت‌های مختلف نام یک نفر را جمع کنید تا متغیر `fullName` حاوی نام کامل وی باشد.
{% initial %}
var firstName = "John";
var lastName = "Smith";

var fullName =
{% solution %}
var firstName = "John";
var lastName = "Smith";

var fullName = firstName + " " + lastName;
{% validation %}
assert(fullName === 'John Smith');
{% endexercise %}
