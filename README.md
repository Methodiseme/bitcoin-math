# monero-math

Provides number prototypes for converting between XMR and Satoshi values. It
uses string based parsing, which avoids JavaScript's nasty problem of doing
weird things with integer division.

Also adds a zeropad method for making full length XMR strings


# TOC
   - [Number.toMonero()](#numbertomonero)
   - [Number.toSatoshi()](#numbertosatoshi)
   - [Number.zeroFill()](#numberzerofill)

<a name=""></a>
 
<a name="numbertomonero"></a>
# Number.toMonero()
should add the toMonero function to the Number object.

```js
var num = 1;
assert(num.toMonero);
```

should return a monero value derived from the number.

```js
var satoshi = 100000000000;
assert(satoshi.toMonero() === 0.1);
```

should return NaN if the original is NaN.

```js
var bad = NaN;
assert(isNaN(bad.toMonero()));
```

<a name="numbertosatoshi"></a>
# Number.toSatoshi()
should add the toSatoshi function to the Number object.

```js
var num = 1;
assert(num.toSatoshi);
```

should return a satoshi value derived from the number.

```js
var monero = 1;
assert(monero.toSatoshi() === 1000000000000);
```

should return NaN if the original is NaN.

```js
var bad = NaN;
assert(isNaN(bad.toSatoshi()));
```

<a name="numberzerofill"></a>
# Number.zeroFill()
should add the zeroFill function to the Number object.

```js
var num = 1;
assert(num.zeroFill);
```

should return a decimal with zeros added (1 => 1.000000000000).

```js
var monero = 1;
assert(monero.zeroFill() === "1.000000000000");
```

should return a decimal with zeros added (1.123 => 1.123000000000).

```js
var monero = 1.123;
assert(monero.zeroFill() === "1.123000000000");
```

should return NaN if the original is NaN.

```js
var bad = NaN;
assert(isNaN(bad.zeroFill()));
```



