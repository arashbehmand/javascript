# توابع درجات بالاتر

توابع پیچده‌تری می‌توان تعریف کرد که بر روی توابع دیگر عملیات انجام می‌دهند.
برای مثال، تابعی می‌تواند تابع دیگری را به عنوان آرگومان بپذیرد و/یا تابعی را به عنوان خروجی برگرداند.در زیر دو تابع `add_2` و `double`  و تابعی درجه بالا با نام `map` را تعریف کرده‌ایم. `map` دو آرگومان می‌گیرد، `func` و `list` و یک آرایه برمی‌گرداند. عمکرد تابع به این شکل است که `func` را بر روی عناصر موجود در `list` اعمال می‌کند و در آرایه خروجی برمی‌گرداند.

```javascript
// تعریف دو تابع ساده
var add_2 = function(x) {
    return x + 2;
};
var double = function(x) {
    return 2 * x;
};

// map تابعی زیباست که دو آرگومان می‌گیرد
//  func	تابعی که باید اجرا شد
//  list	آرایه‌ای از مقادیر که تابع باید روی آنها اجرا شود
var map = function(func, list) {
    var output=[];              // output list
    for(idx in list) {
        output.push( func(list[idx]) );
    }
    return output;
}


// می‌توانیم از «map» برای اعمال تابعی به روی لیستی از مقادیر و گرفتن خروجی‌های متناظر استفاده کنیم
map(add_2, [5,6,7]) // => [7, 8, 9]
map(double, [5,6,7]) // => [10, 12, 14]
```
توابع مثال بالا ساده هستند. اما با استفاده از آنها به عنوان آرگومان توابع دیگر می‌توان کارهای پیچیده‌تری انجام داد.

برای مثال اگر متوجه شدیم که از عبارت `map(add_2, ...)` یا `map(double, ...)` را مکررا به کار برده‌اید، می‌توانید توابعی خاص منظوره برای این توابع تعریف کنید. با استفاده از کد زیر می‌توان این کار را کرد:

```javascript
process_add_2 = function(list) {
    return map(add_2, list);
}
process_double = function(list) {
    return map(double, list);
}
process_add_2([5,6,7]) // => [7, 8, 9]
process_double([5,6,7]) // => [10, 12, 14]
```

در اینجا تابعی به نام `buildProcessor` می‌نویسیم که تابعی به نام `func` را ورودی می‌گیرد
و تابعی را برمی‌گرداند که `func` را بر روی یک لیست اعمال می‌کند.

```javascript
// تابعی که تابعی دیگر می‌سازد تا بر روی لیست عملیاتی انجام دهد.
var buildProcessor = function(func) {
    var process_func = function(list) ف{
        return map(func, list);
    }
    return process_func;
}
// اجرای تابع فوق تابعی دیگر را بر می‌گرداند که یک لیست را به عنوان آرگومان می‌پذیرد و روی آن عملیاتی انجام می‌دهد.


// using buildProcessor we could generate the add_2 and double list processors as follows:
process_add_2 = buildProcessor(add_2);
process_double = buildProcessor(double);

process_add_2([5,6,7]) // => [7, 8, 9]
process_double([5,6,7]) // => [10, 12, 14]
```

بیاید به مثالی دیگر بپردازیم.
تابعی به نام `buildMultiplier` می‌نویسیم که عدد `x` را به عنوان ورودی می‌گیرد و تابعی را برمی‌گرداند که حاصل ضرب ورودیش در `x` را برمی‌گرداند :

```javascript
var buildMultiplier = function(x) {
    return function(y) {
        return x * y;
    }
}

var double = buildMultiplier(2);
var triple = buildMultiplier(3);

double(3); // => 6
triple(3); // => 9
```

{% exercise %}
تابعی به نام `negate` بنویسید که `add` را به عنوان آرگومان بگیرید و تابعی را به عنوان خروجی برگرداند که منفی شده حاصل `add1` را برگرداند.
{% initial %}
var add1 = function (x) {
    return x + 1;
};

var negate = function(func) {
    // TODO
};

// Should return -6
// Because (5+1) * -1 = -6
negate(add1)(5);

{% solution %}
var add1 = function (x) {
    return x + 1;
}

var negate = function(func) {
    return function(x) {
        return -1 * func(x);
    }
}

negate(add1)(5);
{% validation %}
assert(negate(add1)(5) === -6);
{% endexercise %}
