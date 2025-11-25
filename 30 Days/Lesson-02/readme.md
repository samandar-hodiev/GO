
# Day 2 — Syntax Overview

- package
- import
- main function
- Println, Printf, Print
- Comments (//, /* */)

<br><br>

# package

- ### Har bir `.go` fayl boshida `package <nom>` bo‘lishi shart

- ### Bir papkadagi barcha `.go` fayllar bir xil package nomidan foydalanadi

- ### package main faqat executable uchun.Bu package ichida albatta `func main()` bo‘lishi kerak. Aks holda hech nima ishga tushmaydi.

- ### Package nomi kichik harflarda bo‘ladi

- ### Export qilinadigan `funksiyalar`, `structlar`, `o‘zgaruvchilar` katta harf bilan boshlanadi

- ### Package nomi papka nomi bilan mos tushishi tavsiya qilinadi

- ### Keraksiz import bo‘lsa, Go darrov error beradi

- ### Cikli import taqiqlangan `Cikli import = Package A B’ni import qiladi, B A’ni import qiladi. Natija = Error.`

- ### `go.mod` bo‘lmasa, `import` chalkashadi. Projectni modul sifatida yuritish uchun go mod init shart.

- ### Bir faylda faqat bitta package bo‘ladi




<br><br><br>

# import


### Go’da import nima qiladi?

>Boshqa papkadagi (package’dagi) funksiyalarni ishlatishga ruxsat beradi.

```
import "fmt"

func main() {
    fmt.Println("Salom")
}

```

- `fmt` nomli package’ni chaqiradi, keyin uning funksiyalarini ishlatish mumkin bo‘ladi.


<br><br><br>

# main function

> Go dasturi ishga tushganda eng birinchi bo‘lib aynan `main()` funksiyasi ishlaydi.

<br>

### 1) `main` faqat `package main`ichida bo‘ladi, buni buzish hatolikka olibkeladi.

```
package main

func main() {
}
```

<br>

### 2) main hech nima qabul qilmaydi va hech nima qaytarmaydi.


- Noto'g'ri


`func main(a int) {}`
`func main() int {}`


- To'g'ri

`func main() {}`

<br>

### 3) Programmani start nuqtasi — faqat bitta `main()` funksiyasi.

>Bir nechta main bo‘lishi mumkin emas. Dastur qaysi biridan boshlanishini bilmay qoladi.

<br>

### 4) `main.go` fayl nomi majburiy emas, faqat `package main` bo‘lsa bo‘ldi.

- Uchta fayl bo‘lsa ham bo‘ladi:

```
cmd/
   run.go
   start.go
   print.go
```

- Dastur baribir `main()` funksiyasini topib ishlaydi.

```
package main
```

<br>

### `main()` funksiyasi:

- faqat package main ichida bo‘ladi
- parametrlari bo‘lmaydi
- return qilmaydi
- dastur shu yerda boshlanadi
- bitta bo‘lishi kerak


<br><br><br>


# `Println`, `Printf`, `Print` ...

- `print` va `println` — tilda ichki, faqat tez `debugging` uchun; xatti-harakatlari implementatsiyaga bog‘liq va rasmiy format kafolatlanmagan. `println` oxirida yangi qator qo‘yadi, `print` qo‘ymaydi. Ishonchli, production-ga oid vosita emas.

- `fmt.Print` — argumentlarni chiqaradi, yangi qator qo‘ymaydi.

- `fmt.Println` — argumentlar orasiga bo‘sh joy qo‘yadi va oxirida yangi qator qo‘yadi.

- `fmt.Printf` — format string bilan ishlaydi (formatlash, width, precision, verb-lar va hokazo).

- `fmt.Fprint` / `Fprintln` / `Fprintf` — xuddi yuqoridagilar, lekin natijani istalgan `io.Writerga` yozadi (masalan `fayl` yoki `http.ResponseWriter`).


<br>

---

# `fmt.Print`

> Argumentlarni ketma-ket chiqaradi, yangi qator qo‘ymaydi.

```
fmt.Print("a", 1) // "a1"
```

<br>

# `fmt.Println`

> Argumentlar orasiga bo‘sh joy qo‘yadi va oxirida yangi qator `\n` qo‘yadi.

```
fmt.Println("a", 1) // "a 1\n"
```

<br>

# `fmt.Printf`

> Format verb’lari va qoidalari.

### Eng ko‘p ishlatiladigan verb’lar:

- `%v` — default qiymat (general).

- `%+v` — struct uchun maydon nomlari bilan.

- `%#v` — Go-syntax ko‘rinishida (reproducible).

- `%T` — qiymat turi.

- `%d` — onlik integer.

- `%b` — binary.

- `%o` — octal.

- `%x`, `%X` — hex.

- `%f` — float (decimal notation).

- `%e` — scientific (1.23e+03).

- `%g` — compact float (choose %e or %f).

- `%s` — string (raw).

- `%q` — quoted string ("..." with escapes).

- `%t` — boolean.

- `%p` — pointer address.

- `%c` — rune as character.

<br>

### Flag va width/precision misoli:

- `%-10s` — chapga hizalash, width = 10.

- `%010d` — 0 bilan to‘ldirish, width = 10.

- `%.2f` — float uchun precision = 2.

---