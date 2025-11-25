

## **Day 1 — Installation & Setup**
- Install Go
- GOROOT, GOPATH understanding
- Project structure
- go mod init, go run, go build
- First program (main.go)



<br><br>

## 1️⃣ GOROOT

---
> Bu – Go tilining o‘rnatilgan joyi (Go kompilyatori va standart kutubxonalar saqlanadigan joy).

- Odatda siz uni o‘zgartirmaysiz.

- Misol: C:\Go yoki /usr/local/go

- Qoidasi: Go o‘zining standart paketlarini shu joydan yuklaydi.


       go env GOROOT

---
<br>

## 2️⃣ GOPATH

> Bu – sizning ish loyihalaringiz va o‘rnatgan tashqi paketlaringiz joylashgan katalog.

- Masalan, sizning loyihalaringiz va pkg, bin, src papkalaringiz shu yerda bo‘ladi.

- Misol: C:\Users\Samandar\go

- Qoidasi: Sizning yozgan kodlaringiz va boshqa kutubxonalar shu joyda bo‘lishi kerak, shunda Go ularni topa oladi.

        go env GOPATH

<br>

## Oddiy eslab qolish:

> GOROOT → Go’ning “o‘zi”

> GOPATH → Sizning “kodlaringiz va paketlaringiz”



<br><br><br><br>

# Project structure


```
├── .git
├── cmd
|   └── myapp
|       └── main.go
├── examples
|   └── example1
|       └── main.go
├── internal
|   ├── config
|   |   └── config.go
|   └── store
|       └── store.go
├── pkg
|   ├── public1
|   |   └── public1.go
|   └── public2
|       └── public2.go
├── go.mod
└── go.sum
```

<br><br><br><br>

# go mod init, go run, go build


<br>

## go mod init

>Go tilida loyihalarni boshqarish uchun module system ishlatiladi. go mod init bu loyihangiz uchun module yaratadi. Module — bu sizning Go loyihangizdagi paketlarni va ularning bog‘liqliklarini (dependencies) boshqarish usulidir.

```
go mod init <module_name>
```

<br>

## go run

> "go run" bu Go faylini to‘g‘ridan-to‘g‘ri ishga tushirish uchun ishlatiladi. Siz faylni kompilyatsiya qilmasdan darhol bajarishingiz mumkin.

```
go run <file_name>.go
```

<br>

## go build

>"go build" bu Go fayllarini kompilyatsiya qilib, ishga tushadigan executable fayl hosil qiladi.

```
go build <file_name>.go
```

>Agar fayl nomini bermasangiz, go build joriy katalogdagi main package ni kompilyatsiya qiladi va executable fayl yaratadi.

```
go build main.go
```

Natija:

- Windowsda `main.exe`
- MacOS/Linuxda `main` fayli hosil bo‘ladi.

Uni keyin quyidagicha ishga tushirish mumkin:

```
./main   # Mac/Linux
main.exe # Windows
```

| Buyruq     | Maqsad                                                 |
| ---------- | ------------------------------------------------------ |
| `go run`   | Faylni kompilyatsiya qilmasdan darhol ishga tushiradi  |
| `go build` | Faylni kompilyatsiya qiladi va executable hosil qiladi |
