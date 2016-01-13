# توابع پیچیده‌تر

توابع پیچده‌تری می‌توان تعریف کرد که بر روی توابع دیگر عملیات انجام می‌دهند.
برای مثال، تابعی می‌تواند تابع دیگری را به عنوان آرگومان بپذیرد و/یا تابعی را به عنوان خروجی برگرداند.

We will now create two simple functions, `add_2` and `double`, and a higher order function called `map`. `map` will accept two arguments, `func` and `list` (its declaration will therefore begin `map(func,list)`), and return an array. `func` (the first argument) will be a function that will be applied to each of the elements in the array `list` (the second argument).

```javascript
// Define two simple functions
var add_2 = function(x) {
    return x + 2;
};
var double = function(x) {
    return 2 * x;
};

// map is cool function that accepts 2 arguments:
//  func    the function to call
//  list    a array of values to call func on
var map = function(func, list) {
    var output=[];              // output list
    for(idx in list) {
        output.push( func(list[idx]) );
    }
    return output;
}


// We use map to apply a function to an entire list
// of inputs to "map" them to a list of corresponding outputs
map(add_2, [5,6,7]) // => [7, 8, 9]
map(double, [5,6,7]) // => [10, 12, 14]
```

The functions in the above example are simple. However, when passed as arguments to other functions, they can be composed in unforeseen ways to build more complex functions.

For example, if we notice that we use the invocations `map(add_2, ...)` and `map(double, ...)` very often in our code, we could decide we want to create two special-purpose list processing functions that have the desired operation baked into them. Using function composition, we could do this as follows:

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
// a function that generates a list processor that performs
var buildProcessor = function(func) {
    var process_func = function(list) {
        return map(func, list);
    }
    return process_func;
}
// calling buildProcessor returns a function which is called with a list input


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
