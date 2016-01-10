# حلقه‌ها

حلقه‌ها برای انجام کار‌های تکراری استفاده می‌شوند.

با حلقه می‌توانید به جای:

```javascript
doThing(cars[0]);
doThing(cars[1]);
doThing(cars[2]);
doThing(cars[3]);
doThing(cars[4]);
```

بنویسید:

```javascript
for (var i=0; i < cars.length; i++) { 
    doThing(cars[i]);
}
```