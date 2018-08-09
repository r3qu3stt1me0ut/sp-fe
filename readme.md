# sp-fe-beta

>Common function for Date, Array, Parse Data etc.

## Install

``` node
npm install --save sp-fe-beta
```

## Usage

```js
const sp = require('sp-fe-beta'); //sp: {date, array, parse}
sp.date.format('yyyy-MM-dd', new Date());
//=> 2018-08-06
sp.array.sort(arr = [1, 2, 3, 4, 1], isASC = true)
//=>[1, 1, 2, 3, 4]
sp.array.sort(arr = [1, 2, 3, 4, 1], isASC = false)
//=>[4, 3, 2, 1, 1]
```

### Date

```js
const date = require('sp-fe-beta/date');
date.format('yyyy-MM-dd', new Date());
//=> 2018-08-06
date.goto(year, month, day);
//=> return Date
date.prevDay(dayCount = 0, startDate = new Date());
//=> return Date
date.prevMonth(monthCount = 0, date = new Date());
//=> return Date
date.prevYear(yearCount = 0, date = new Date());
//=> return Date
date.nextDay(dayCount = 0, startDate = new Date());
//=> return Date
date.nextMonth(monthCount = 0, date = new Date());
//=> return Date
date.nextYear(yearCount = 0, date = new Date());
//=> return Date
date.calc(startDate = new Date(2018, 01, 01), endDate = new Date());
//=> { seconds: 20, minutes: 44, hours: 15, days: 188 }
date.calc(startDate = new Date(2018, 01, 01), endDate = new Date(2000, 01, 01));
//=> { seconds: 0, minutes: 0, hours: 0, days: 6575 }
```

### Array && Array of Objects

```js
const arr = require('sp-fe-beta/array');
arr.create((length = 5, fillVal = 'a'))
//=>['a', 'a', 'a', 'a', 'a']
arr.sort(arr = [1, 2, 3, 4, 1], isASC = true)
//=>[1, 1, 2, 3, 4]
arr.sort(arr = [1, 2, 3, 4, 1], isASC = false)
//=>[4, 3, 2, 1, 1]
arr.sortObj(arr = [{name: 'Alice', age: 12},{name: 'Bob', age: 14}, {name: 'John', age: 11}, {name: 'Dannise', age: 9}], keyName = 'age', isASC = true)
//=>[{name: 'Dannise', age: 9}, {name: 'John', age: 11}, {name: 'Alice', age: 12},{name: 'Bob', age: 14}]
arr.sortObj(arr = [{name: 'Alice', age: 12},{name: 'Bob', age: 14}, {name: 'John', age: 11}, {name: 'Dannise', age: 9}], keyName = 'age', isASC = false)
//=>[{name: 'Bob', age: 14}, {name: 'Alice', age: 12}, {name: 'John', age: 11}, {name: 'Dannise', age: 9}]
arr.unique(arr = [1, 2, 3, 4, 1])
//=>[1, 2, 3, 4]
arr.uniqueObj(arr = [{a: 1, b: 2}, {a: 2, b: 3}, {a: 1}], keyName = 'a')
//=>[{a: 1, b: 2}, {a: 2, b: 3}]
arr.uniqueObj(arr = [{a: 1, b: 2}, {a: 2, b: 3}, {a: 1}], keyName = 'a', isDeep = true)
//=>[{a: 1, b: 2}, {a: 2, b: 3}, {a: 1}]
arr.filter(arr = [1, 3, 4, 5], function(item) {return item > 3;})
//=>[4, 5]
arr.filter(arr = [{name: 'Alice', age: 12},{name: 'Bob', age: 14}, {name: 'John', age: 11}, {name: 'Dannise', age: 9}], function(item) {return item.age > 12;})
//=>[{name: 'Bob', age: 14}]
```

### Parse

```js
const parse = require('sp-fe-beta/parse');
parse.number(num = [], fixedLength = 0) //undefined, [] ,{} ,NaN ,'' ,' ', null or not number string return 0
//=> 0
parse.number(num = {}, fixedLength = 2)
//=> 0.00
parse.number(num = 'a', fixedLength = 2)
//=> 0.00
parse.number(num = '2', fixedLength = 2)
//=> 2.00
parse.number(num = '2.000', fixedLength = 2)
//=> 2.00
parse.boolean(0) //undefined, [] ,{} ,NaN ,'' ,' ', null return false
//=> false
parse.boolean('a') //undefined, [] ,{} ,NaN ,'' ,' ', null return false
//=> true
```

## License

MIT