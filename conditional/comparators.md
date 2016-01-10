# مقایسه‌گر‌ها

به قسمت عبارت شرطی توجه کنید:

```javascript
if (country === "France") {
    ...
}
```

قسمت شرطی متغییر `country` است که بعد از آن سه علامت مساوی آمده (`===`). سه علامت مساوی بررسی می‌کنند که متغییر `country` مقدار صحیح (`France`) را داشته باشد و همچنین از نوع مورد نظر (`String`) باشد. شما می‌توانید عبارات شرطی‌ای با دو مساوی نیز داشته باشید. هرچند در این صورت عبارت شرطی `if (x == 5)` هم برای `var x = 5;` و هم  `var x = '5';` درست خواهد بود. بسته به اینکه برنامه چه کاری باید انجام دهد این مسئله می‌تواند تعیین کننده باشد.  اکیدا توصیه شده است که برابری را با سه مساوی (`===` and `!==`) به جای دو مساوی (`==` and `!=`) بررسی کنید.

سایر بررسی‌های شرطی:

* ```x > a```: آیا x بزرگتر از a است؟
* ```x < a```: آیا x کوچکتر از a است؟
* ```x <= a```: آیا x کوچکتر از یا مساوی با a است؟
* ```x >=a```: آیا x بزرگتر از یا مساوی با a است؟
* ```x != a```: آیا x برابر a نیست؟
* ```x```: آیا x وجود دارد؟


{% exercise %}
شرطی اضافه کنید که مقدار `a` را به 10 تغییر دهد اگر `x` بزرگتر از 5 باشد.
{% initial %}
var x = 6;
var a = 0;
{% solution %}
var x = 6;
var a = 0;

if (x > 5) {
    a = 10;
}
{% validation %}
assert(a === 10);
{% endexercise %}

##Logical Comparison

In order to avoid the if-else hassle, simple logical comparisons can be utilised.

```js
var topper = (marks > 85) ? "YES" : "NO";
```

In the above example, `?` is a logical operator. The code says that if the value of marks is greater than 85 i.e. `marks > 85` , then `topper = YES` ; otherwise `topper = NO` . Basically, if the comparison condition proves true, the first argument is accessed and if the comparison condition is false , the second argument is accessed.
