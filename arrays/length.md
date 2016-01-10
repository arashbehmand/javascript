# طول

آرایه‌ها ویژگی ای به نام `length` دارند که همانطور که به نظر می‌رسد، طول آرایه را می‌دهد.

```javascript
var array = [1 , 2, 3];

// Result: l = 3
var l = array.length;
```

{% exercise %}
متغییری تعریف کنید و مقدار طول آرایه زیر را در آن بریزید.
{% initial %}
var array = [1, 1, 2, 3, 5, 8];
var l = array.length;
var a =
{% solution %}
var array = [1, 1, 2, 3, 5, 8];
var l = array.length;
var a = 6;
{% validation %}
assert (a === 6)
{% endexercise %}
