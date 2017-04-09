## The if statement

Until now, the *programs* we've seen were all very straight forward and incapable of doing something interesting. We know computers can do more, but how?

Imagine you want to define a variable with how much days an year has. It seems simple, we have already done it, right? Yeah, kinda... If it is a leap year, how would you assign your variable?

Enters the if statement.

By now we would have something like

```javascript
var daysInYear = 365;
```

With the help of the *if* statement we can do something like

```javascript
var daysInYear = 365;

if(isLeapYear) {
  daysInYear = 366;
}
```

The **if** statement evaluates a boolean expression and executes the code between `{}` if that boolean expression is **true**. We can use logical and relational operators inside *if* statements.

```javascript
var daysInYear;

if(isLeapYear) {
  daysInYear = 366;
}

if(!isLeapYear) {
  daysInYear = 365
}
```

To do things like the lines above, programming languages have the `else` statement.

```javascript

var daysInYear = 0;

if(isLeapYear) {
  daysInYear = 366;
}else {
  daysInYear = 365
}
```

## Loops

A loop is a program structure that executes the same piece of code zero or more times. It is a group of statements (or a block) and a boolean expression, called **condition**. 

Every time the code inside the loop executes, the expression is evaluated, if it is still true, the loop executes again, until the condition is false. Each execution of the loop is called an **iteration**.

```javascript
var counter = 0;
var sum = 0;

while (counter > 10) {
  sum = sum + 5;
  
  console.log(sum);
  counter = counter + 1;
}

// 1 - counter = 0 | sum = 0
// 2 - counter = 1 | sum = 5
// 3 - counter = 2 | sum = 10
// ...
// 10 - counter = 10 | sum = 50
```

### Array using a for statement

```javascript
var shopinglist = ["eggs", "bread", "water", "milk"];

for (var position = 0; position < 4; position ++) {
  console.log (shopinglist [position])
}
// 1 - position = 0 | shopinglist = eggs
// 2 - position = 1 | shopinglist = bread
// 3 - position = 2 | shopinglist = water
// 4 - position = 3 | shopinglist = milk
```




