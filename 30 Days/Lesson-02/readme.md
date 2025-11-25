
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