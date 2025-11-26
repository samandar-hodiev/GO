# Day 3 — Variables & Constants

- var keyword & zero-values
- `short declaration (:=)`
- multiple variables
- constants (const)
- type inference

<br><br><br>

# var

> `var` Go’da o‘zgaruvchi e’lon qilish uchun ishlatiladi.

```
var x int
```

> Bu: `x degan integer bor, hozircha qiymati 0` degani.

<br>

## `zero-values`

### Go’da e’lon qilingan o‘zgaruvchiga darhol default qiymat beriladi:

#### 1. `Sonli turlar`

| Tip                                        | Default |
| ------------------------------------------ | ------- |
| int, int8, int16, int32, int64             | 0       |
| uint, uint8 (byte), uint16, uint32, uint64 | 0       |
| rune (int32 alias)                         | 0       |
| uintptr                                    | 0       |

<br>


#### 2. `Floating-point turlar`

| Tip     | Default |
| ------- | ------- |
| float32 | 0       |
| float64 | 0       |

<br>

#### 3. `Complex sonlar`

| Tip        | Default |
| ---------- | ------- |
| complex64  | (0+0i)  |
| complex128 | (0+0i)  |

<br>

#### 4. `Boolean`

| Tip  | Default |
| ---- | ------- |
| bool | false   |

<br>

#### 5. `String`

| Tip    | Default |
| ------ | ------- |
| string | ""      |

<br>

#### 6. `Pointerlar`

| Tip          | Default |
| ------------ | ------- |
| *T (pointer) | nil     |

<br>

#### 7. `Slices`

| Tip                  | Default |
| -------------------- | ------- |
| []int, []string, ... | nil     |


<br>

#### 8. `Maps`

Default: nil map

```
var m map[string]int // nil
```

<br>

#### 9. `Channels`

Default: nil channel

```
var ch chan int // nil
```

<br>

#### 10. `Interfaces`

Default: nil

```
var x interface{} // nil
```

<br>

#### 11. `Functions`

> funksiya tipini ham o‘zgaruvchi sifatida saqlash mumkin.

Default: nil

```
var fn func(int) int // nil

```

<br>

#### 12. Arrays

Arrays slice emas, shuning uchun default qiymat ichidagi elementlar defaultiga qarab to‘ladi.

```
var a [3]int   // [0 0 0]
var b [3]bool  // [false false false]
var c [3]string // ["", "", ""]

```
<br>

#### 13. Structs

Structdagi har bir field o‘zining default qiymatiga qarab to‘ladi.

```
type User struct {
    Name string
    Age  int
    On   bool
}

var u User
// {Name:"", Age:0, On:false}
```

<br>
<br>
<br>

---

# short declaration `:=`


>Short declaration degani `:=` operatori bo‘lib, u faqat `funksiya ichida ishlaydi` va o‘zgaruvchini e’lon qilish va  qiymat berishni bir vaqtning o‘zida bajaradi. Go tipni qiymatga qarab o‘zi aniqlaydi.

<br>

MISOL:

```
x := 10      // int
name := "A"  // string
ok := true   // bool
```
<br>

- Paket darajasida ishlamaydi.
- Kamida bitta yangi o‘zgaruvchi bo‘lishi shart:

```
a := 5
a, b := 10, 20   // b yangi bo‘lgani uchun OK
```

---

<br><br><br>

---
# constants `const`

### 1. `Faqat compile-time qiymat bo‘lishi kerak`

const ga faqat aniq, literal qiymat beriladi.

To'g'ri:

```
const x = 10
const s = "hello"
```

Noto'g'ri:

```
var n = 5
const y = n   // ERROR: const ga runtime qiymat berilmaydi
```
<br>

### 2. `Tip berilmasa ham bo‘ladi`

const default bo‘lib untyped bo‘ladi.

```
const a = 10        // untyped int
const b = 3.14      // untyped float
const c = "test"    // untyped string

```
Bu untyped bo‘lgani uchun kerak bo‘lsa har xil tipga moslashadi:

```
var x float64 = a   // OK
var y int = a       // OK
```

<br>

### 3. `Bir nechta e’lon qilish mumkin`

```
const (
    A = 1
    B = 2
    C = 3
)
```

<br>


### 4. `Expression ishlatish mumkin`

Literallardan iborat bo‘lsa, arifmetika ishlaydi.

```
const r = 10
const area = r * r  // OK

```

<br>

### 5. `String va number eng ko‘p ishlatiladi`

`Map`, `slice`, `struct`, `array` qilib `const` chiqarib bo‘lmaydi.


Xato:
```
const arr = [3]int{1,2,3}  // ERROR
```

<br><br>

## `const bu`:

- faqat funksiya ichida emas, butun package bo‘ylab ishlaydi
- qiymat o‘zgarmaydi
- faqat literal va compile-time hisoblashlar bo‘ladi
- type optional
- slice, map, struct uchun ishlamaydi

---

<br><br><br>

# Type inference.

> Type inference – bu `Go` kompilyatori o‘zgaruvchining turini berilgan qiymatga qarab avtomatik aniqlash qobiliyati.