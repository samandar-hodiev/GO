
## **Day 5 — Operators**

- Arithmetic
- Comparison
- Logical
- Assignment
- Bitwise
- Operator precedence


<br><br><br><br><br>

# Arithmetic Operators

## Addition `+`

> Qiymatlarni qo‘shish uchun ishlatiladi.

```
a := 5
b := 3
c := a + b // 8
```

<br>

## Subtraction `-`

>Qiymatlarni ayirish uchun ishlatiladi.

```
d := a - b // 2
```

<br>

## Multiplication `*`

> Qiymatlarni ko‘paytirish uchun ishlatiladi.

```
e := a * b // 15
```
<br>

## Division `/`

> Qiymatlarni bo‘lish uchun ishlatiladi.

> Agar integer / integer bo‘lsa, natija faqat butun son bo‘ladi (kasr qismini tashlab yuboradi).

```
f := 7 / 3  // 2
g := 7.0 / 3.0 // 2.333333 (float)
```
<br>

## Modulo `%`

> Qiymatlarni bo‘lgandan qoldiqni topadi.

```
h := 7 % 3 // 1
```
<br>

## Unary plus `+` va minus `-`

> Qiymatning imzosini o‘zgartirish yoki shunchaki ijobiy qilish uchun ishlatiladi.

```
i := -a  // -5
j := +a  // 5
```

<br>


> Arithmetic operatorlar faqat numeric turlar bilan ishlaydi: int, uint, float32/64, complex64/128.

> Turini aralashtirish uchun explicit type conversion talab qilinadi.

```
var a int = 5
var b float64 = 2.5
c := float64(a) + b // 7.5
```

> Bo‘lishda 0 ga bo‘lish xato beradi - runtime panic.
> Integer bo‘lsa, `/` operatori butun son qaytaradi, float bo‘lsa kasrli son.

<br><br><br><br><br>

# Comparison

<br>

| Operator | Ma’nosi          | Misol    | Natija                 |
| -------- | ---------------- | -------- | ---------------------- |
| `==`     | Tenglik          | `a == b` | true agar a = b bo‘lsa |
| `!=`     | Teng emaslik     | `a != b` | true agar a ≠ b bo‘lsa |
| `<`      | Kichik           | `a < b`  | true agar a < b bo‘lsa |
| `<=`     | Kichik yoki teng | `a <= b` | true agar a ≤ b bo‘lsa |
| `>`      | Katta            | `a > b`  | true agar a > b bo‘lsa |
| `>=`     | Katta yoki teng  | `a >= b` | true agar a ≥ b bo‘lsa |


<br>

> Numeric turlar (int, uint, float, complex) va string turlari bilan ishlaydi.
> Boolean turlari bilan ham ishlaydi:

```
var x bool = true
var y bool = false
fmt.Println(x == y) // false
```

> Different type comparison → explicit type conversion talab qiladi.

```
var a int = 5
var b float64 = 5.0
fmt.Println(float64(a) == b) // true
```

> Complex numbers faqat tenglik (==, !=) bilan solishtiriladi, <, > ishlamaydi.
> Strings lexicographical order bo‘yicha taqqoslanadi (ASCII/UTF-8 qiymatlariga qarab).

```
fmt.Println("abc" < "bcd") // true
```

```
package main
import "fmt"

func main() {
    a := 5
    b := 10
    fmt.Println(a == b)  // false
    fmt.Println(a != b)  // true
    fmt.Println(a < b)   // true
    fmt.Println(a <= b)  // true
    fmt.Println(a > b)   // false
    fmt.Println(a >= b)  // false

}
```

> Comparison operators - qiymatlarni taqqoslash, boolean natija qaytaradi (true yoki false), faqat mos turlar bilan ishlaydi va complex sonlarda `<`, `>` ishlamaydi.