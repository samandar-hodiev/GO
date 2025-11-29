# Day 4 — FULL Go Data Types

<br>

## Boolean

- bool

<br>

## Numeric Types

#### `Signed Integers:`

- int
- int8
- int16
- int32
- int64

#### `Unsigned Integers:`

- uint
- uint8 (byte)
- uint16
- uint32
- uint64
- uintptr

#### `Floating Points:`

- float32
- float64

#### `Complex Numbers:`

- complex64
- complex128

#### `Text Types`

- string
- byte (alias uint8)
- rune (alias int32)

#### `Composite Types`

- array
- slice
- map
- struct
- pointer
- channel
- interface
- function types

#### `Special Types`

- error
- nil

<br><br><br><br>

![alt text](image.png)

<br><br><br><br>

# Primitive (Asosiy) turlar

> Primitive turlar oddiy qiymatlarni ifodalaydi va ular by value ishlaydi (ya’ni, o‘zgaruvchi nusxasi o‘zgartirilganda asl qiymat o‘zgarmaydi). Golangda ular quyidagilar:

| Tur                                           | Misol                     | Izoh                |
| --------------------------------------------- | ------------------------- | ------------------- |
| `int`, `int8`, `int16`, `int32`, `int64`      | `var a int = 5`           | Butun sonlar        |
| `uint`, `uint8`, `uint16`, `uint32`, `uint64` | `var b uint = 10`         | Musbat butun sonlar |
| `float32`, `float64`                          | `var c float64 = 3.14`    | Haqiqiy sonlar      |
| `complex64`, `complex128`                     | `var d complex128 = 1+2i` | Murakkab sonlar     |
| `bool`                                        | `var e bool = true`       | Mantiqiy qiymat     |
| `string`                                      | `var f string = "hello"`  | Matnlar             |
| `byte` (alias `uint8`)                        | `var g byte = 255`        | Asosiy bayt turi    |
| `rune` (alias `int32`)                        | `var h rune = 'a'`        | Unicode belgilar    |

> Primitive turlar odatda “atomic” qiymatlar, ya’ni ularni oson nusxalash va solishtirish mumkin.

<br><br>

# Non-primitive (Murakkab) turlar

> Non-primitive turlar kompleks strukturalar bo‘lib, ular by reference ishlashi mumkin (ya’ni, o‘zgaruvchilar ularning asl qiymatini emas, adresini ushlaydi). Golangda bular:

| Tur         | Misol                                          | Izoh                                |
| ----------- | ---------------------------------------------- | ----------------------------------- |
| `array`     | `var arr [3]int = [3]int{1,2,3}`               | Belgilangan o‘lchamdagi massiv      |
| `slice`     | `var s []int = []int{1,2,3}`                   | O‘lchami dinamik massiv             |
| `map`       | `var m map[string]int = map[string]int{"a":1}` | Kalit-qiymat juftliklari            |
| `struct`    | `type Person struct {Name string; Age int}`    | Maxsus tuzilgan obyekt              |
| `pointer`   | `var p *int = &a`                              | Adres orqali ishlash                |
| `interface` | `var i interface{} = 10`                       | Har qanday turdagi qiymatni saqlash |
| `channel`   | `ch := make(chan int)`                         | Go rutinlararo kommunikatsiya       |
| `function`  | `func() {}`                                    | Funksiyalar ham obyekt sifatida     |

> `Do Not Forget! :` Array by value ishlaydi (ya’ni nusxalash asl qiymatni ko‘chirish), slice va map esa reference sifatida ishlaydi.

<br><br><br><br>

# Go da data turlari asosan 4 ta guruxga bo'linadi ular quyidagilar:

| Guruh               | Turlar misollari                                         | Primitive yoki Non-primitive?                                                                          |
| ------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **Basic types**     | `int`, `float64`, `bool`, `string`, `rune`, `complex128` | **Primitive**                                                                                          |
| **Aggregate types** | `array`, `struct`                                        | Aralash: `array` by value → primitivega yaqin, `struct` by value → non-primitive deb ham qarash mumkin |
| **Reference types** | `slice`, `map`, `pointer`, `channel`, `function`         | **Non-primitive**                                                                                      |
| **Interface types** | `interface{}`                                            | **Non-primitive**                                                                                      |

<br><br><br><br><br><br><br><br>


# Numeric Types


##  `Signed Integers:`

<b>Signed Integers:</b> `int`, `int8`, `int16`, `int32`, `int64`

- Signed integer  -  musbat va manfiy butun sonlarni ifodalay oladigan tur.
- “Signed” degani, qiymat `+` va `-` ikkalasini qabul qiladi.

<br>

### Turlar va xotira hajmi

| Tur     | Xotira (bit)                 | Qiymat oralig‘i                                        |
| ------- | ---------------------------- | ------------------------------------------------------ |
| `int8`  | 8 bit                        | -128 … 127                                             |
| `int16` | 16 bit                       | -32,768 … 32,767                                       |
| `int32` | 32 bit                       | -2,147,483,648 … 2,147,483,647                         |
| `int64` | 64 bit                       | -9,223,372,036,854,775,808 … 9,223,372,036,854,775,807 |
| `int`   | 32/64 bit (platformga qarab) | platformga qarab                                       |


> `int` platformga qarab `32` yoki `64` bit bo‘lishi mumkin. Agar aniq o‘lcham kerak bo‘lsa, `int32` yoki `int64` ishlatish tavsiya qilinadi.



<br><br><br><br><br><br><br><br>

## `Unsigned integer`

<b>Unsigned Integers</b>: `uint`, `uint8`, `uint16`, `uint32`, `uint64`, `uintptr`



- `Unsigned integer` - faqat `musbat butun sonlar` va `0` ni ifodalay oladigan tur.
- “Unsigned” degani `+` qiymatlar uchun mo‘ljallangan, manfiy son qabul qilmaydi.

<br>

### Turlar va qiymat oralig‘i

| Tur                    | Xotira (bit)                    | Qiymat oralig‘i                               |
| ---------------------- | ------------------------------- | --------------------------------------------- |
| `uint8` (alias `byte`) | 8 bit                           | 0 … 255                                       |
| `uint16`               | 16 bit                          | 0 … 65,535                                    |
| `uint32`               | 32 bit                          | 0 … 4,294,967,295                             |
| `uint64`               | 64 bit                          | 0 … 18,446,744,073,709,551,615                |
| `uint`                 | 32/64 bit (platformaga bog‘liq) | 0 … 2³²-1 yoki 0 … 2⁶⁴-1                      |
| `uintptr`              | platformaga bog‘liq             | Pointer adreslarini saqlash uchun ishlatiladi |




<br><br><br><br><br><br><br><br>


## `Floating Points:`


<b>Floating Points:</b> `float32`, `float64`


- `Floating Point` -  haqiqiy sonlar (real numbers), ya’ni kasrli qiymatlarni saqlaydi.

- Float turlari IEEE 754 standartiga asoslangan.

<br>

### Turlar va xotira hajmi

| Tur       | Xotira (bit) | Aniqlik           | Qiymat oralig‘i (taxminiy) |
| --------- | ------------ | ----------------- | -------------------------- |
| `float32` | 32 bit       | ~7 decimal raqam  | ±1.18e-38 … ±3.4e38        |
| `float64` | 64 bit       | ~15 decimal raqam | ±2.23e-308 … ±1.8e308      |

- Agar yuqori aniqlik kerak bo‘lsa (masalan, ilmiy hisob-kitoblarda) `float64` ishlatish tavsiya qilinadi.

- float64 - default float turi Go da.

- float32 - kam xotira, kam aniqlik (~7 raqam)

- float64 - ko‘p xotira, yuqori aniqlik (~15 raqam), Go da default float

```
package main

import "fmt"

func main() {
    var a int = 10
    var b float64 = 2.5

    // fmt.Println(a + b)    // Bu xato.

    // To‘g‘ri yo‘li:
    fmt.Println(float64(a) + b)
}

```




<br><br><br><br><br><br><br><br>

# `Complex Numbers:`

- complex64
- complex128

<br><br>

> Go'dagi `complex64` va `complex128` shunchaki kompleks sonlar (ya’ni real + imaginary shaklidagi sonlar) uchun ishlatiladi.

<br>

### complex64

- float32 real qism
- float32 imag qism
> Ikkisi birlashib 64 bit

### complex128

- float64 real qism
- float64 imag qism
> Jami 128 bit

```
var c1 complex64 = complex(5, 3) // 5 + 3i
var c2 complex128 = 2 + 4i       // shorthand
```


Go ularni oddiy sonlarga o‘xshab ishlatadi:

```
x := 3 + 2i
y := 1 + 4i

z := x + y
fmt.Println(z) // (4+6i)
```

Real va imag qismlarini olish

```
r := real(x) // 3
i := imag(x) // 2
```

### Qachon kerak bo‘ladi?

Complex sonlar asosan:

- matematik simulyatsiyalar
- signallar (DSP)
- fizik modellar
- grafik algoritmlar
- robototexnika




<br><br><br><br><br><br><br><br>


# STRING `Text Types`


- String — belgilar ketma-ketligini saqlaydi.

- Har bir string immutable (o‘zgarmas), ya’ni bir marta yaratilgach, ichidagi belgilarni bevosita o‘zgartirib bo‘lmaydi.

- Stringlar `UTF-8` formatida kodlangan, ya’ni har bir belgi 1 yoki bir nechta baytdan iborat bo‘lishi mumkin.

- String tipidagi qiymat qo‘shish, uzunlik, substring olish kabi operatsiyalarni qo‘llab-quvvatlaydi, lekin bu operatsiyalar yangi string yaratadi, eski string o‘zgarmaydi.

- String va boshqa turdagi ma’lumotlarni ishlatishda type conversion talab qilinadi (masalan, byte slice - string, int - string emas, conversion kerak).

- Default qiymat: `""` (bo‘sh string).


<br><br><br><br><br><br><br><br>


# Golang Composite Types (Murakkab turlar) qoidasiga ko‘ra

## Array

- Belgilangan o‘lchamdagi bir xil turdagi elementlar ketma-ketligi.

- By value ishlaydi - nusxa olinadi, asl array o‘zgarmaydi.

#### `Sintaksis:`

```
var a [3]int = [3]int{1, 2, 3}
```

<br>

## Slice

- Dinamik o‘lchamli massiv.
- By reference ishlaydi - o‘zgarish asl slice ga ta’sir qiladi.

#### `Sintaksis:`

```
s := []int{1, 2, 3}
s[0] = 10 // asl slice o‘zgaradi
```

<br>

## Map

- Kalit-qiymat juftliklarini saqlaydi.
- By reference ishlaydi.

#### `Sintaksis:`

```
m := map[string]int{"a":1, "b":2}
m["a"] = 100
```

<br>

## Struct

- Maxsus tuzilgan tur bo‘lib, turli turlarni birlashtirish imkonini beradi.
- By value ishlaydi, lekin pointer orqali reference qilsa, asl struct o‘zgaradi.

#### `Sintaksis:`

```
type Person struct {
    Name string
    Age  int
}
p := Person{Name:"Ali", Age:20}
```
<br>

# Pointer

- Qiymat manzilini saqlaydi.
- `*` bilan foydalaniladi.

#### `Sintaksis:`
```
var x int = 10
var p *int = &x
*p = 20 // x ham o‘zgaradi
```

<br>

# Channel

- Go rutinlararo kommunikatsiya kanali.
- Qiymat yuborish va olish uchun ishlatiladi.

#### `Sintaksis:`

```
ch := make(chan int)
go func() { ch <- 5 }()
fmt.Println(<-ch)
```
<br>

# Interface

- Har qanday turdagi qiymatni saqlash va ishlatish imkonini beruvchi abstraksiya.

#### `Sintaksis:`

```
var i interface{} = 42
```

<br>

# Function types

- Funksiyalar ham obyekt sifatida ishlatiladi.

#### `Sintaksis:`

```
f := func(a int, b int) int { return a + b }
fmt.Println(f(2,3)) // 5
```

<br>

> Composite types = murakkab, bir nechta qiymat yoki funksiya manzilini saqlash imkonini beradi.

> Ba’zilari by value (array, struct), ba’zilari by reference (slice, map, pointer, channel, interface, function) ishlaydi.

> Asl qiymatga ta’sir qilish yoki o‘zgartirish usuli turga bog‘liq.


<br><br><br><br><br><br><br><br>


# Special Types (Maxsus turlar)

## `error`

- Go da funksiya yoki operatsiya natijasida xatolik yuz berganini bildiruvchi maxsus tur.
- Asosan interface tipidagi tur bo‘lib, bitta metodga ega:

#### Sintaksis:

```
type error interface {
    Error() string
}
```

- Funksiyalar xatolikni qaytarish uchun error tipidan foydalanadi.
- nil qiymat - xatolik yo‘q, boshqa qiymat - xatolik mavjud.

Misol:

```
func divide(a, b int) (int, error) {
    if b == 0 {
        return 0, fmt.Errorf("division by zero")
    }
    return a / b, nil
}
```


## `nil`

- Go da hech qanday qiymatga ega bo‘lmagan obyektni bildiruvchi maxsus qiymat.
- nil quyidagi turlarda ishlatiladi:

  - pointer
  - slice
  - map
  - channel
  - function
  - interface

<br>

- nil bilan tekshirish  obyekt mavjud yoki yo‘qligini aniqlash.

Masalan:

```
var p *int = nil
if p == nil {
    fmt.Println("Pointer is nil")
}
```


>  Special types - Go da maxsus vazifa uchun mo‘ljallangan turlar.

- `error` - xatolikni ifodalaydi, interface sifatida ishlaydi.
- `nil` - hech qanday qiymatga ega emasligini bildiradi, pointer, slice, map, channel, function, interface bilan ishlatiladi.