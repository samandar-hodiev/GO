

## 📅 1-Month Full Go Roadmap

---

# 📌 WEEK 1 — BASICS & FUNDAMENTALS

## **Day 1 — Installation & Setup**
- Install Go
- GOROOT, GOPATH understanding
- Project structure
- go mod init, go run, go build
- First program (main.go)

---

## **Day 2 — Syntax Overview**
- package
- import
- main function
- fmt.Println, Printf
- Comments (//, /* */)

---

## **Day 3 — Variables & Constants**
- var keyword
- short declaration (:=)
- multiple variables
- constants (const)
- zero-values
- type inference

---

## **Day 4 — FULL Go Data Types**

### **Boolean**
- bool

### **Numeric Types**

#### Signed Integers:
- int
- int8
- int16
- int32
- int64

#### Unsigned Integers:
- uint
- uint8 (byte)
- uint16
- uint32
- uint64
- uintptr

#### Floating Points:
- float32
- float64

#### Complex Numbers:
- complex64
- complex128

### **Text Types**
- string
- byte (alias uint8)
- rune (alias int32)

### **Composite Types**
- array
- slice
- map
- struct
- pointer
- channel
- interface
- function types

### **Special Types**
- error
- nil

---

## **Day 5 — Operators**
- Arithmetic
- Comparison
- Logical
- Assignment
- Bitwise
- Operator precedence

---

## **Day 6 — Strings**
- len()
- concatenation
- escape characters
- runes & UTF-8 issues
- string functions (strings package):
  - Contains
  - Replace
  - Split
  - ToUpper
  - Trim

---

## **Day 7 — User Input & Basic Error Handling**
- fmt.Scan / Scanf / Scanln
- simple error handling
- if err != nil pattern

---

# 📌 WEEK 2 — CONTROL FLOW & COLLECTIONS

## **Day 8 — Conditions**
- if / else if / else
- inline short variable in if
- nested conditions

---

## **Day 9 — Switch Statements**
- expression switch
- multiple-case
- no-expression switch
- fallthrough

---

## **Day 10 — Loops**
- for i := ...
- for condition
- infinite loop
- break & continue

---

## **Day 11 — Arrays**
- declaration
- initialization
- length
- fixed size nature

---

## **Day 12 — Slices**
- creation (literal, make)
- length vs capacity
- append
- slicing (a[1:4])
- copy()

---

## **Day 13 — Maps**
- creation
- adding entries
- deleting entries
- check existence: value, ok := m[key]

---

## **Day 14 — Range**
- arrays
- slices
- maps
- strings (rune iteration)

---

# 📌 WEEK 3 — FUNCTIONS, POINTERS, STRUCTS, INTERFACES

## **Day 15 — Functions**
- parameters
- return values
- multiple returns
- named returns
- variadic functions
- anonymous functions

---

## **Day 16 — Pointers**
- & and *
- pointer types
- passing pointers to functions
- pointer vs value semantics

---

## **Day 17 — Structs**
- defining structs
- initializing structs
- nested structs
- anonymous structs

---

## **Day 18 — Methods**
- method declaration
- value receiver
- pointer receiver
- comparison with functions

---

## **Day 19 — Interfaces**
- defining interfaces
- automatic implementation
- empty interface
- polymorphism through interfaces

---

## **Day 20 — Type Assertions & Type Switch**
- value.(T)
- comma-ok form
- type switch for interface values

---

## **Day 21 — Error Handling**
- errors.New
- fmt.Errorf
- custom error types
- error patterns

---

# 📌 WEEK 4 — FILE I/O, JSON, CONCURRENCY & PACKAGES

## **Day 22 — Packages**
- creating a package
- folder structure
- exporting names
- importing local modules

---

## **Day 23 — File Handling**
- os.Open
- os.Create
- ReadFile, WriteFile
- file read/write operations

---

## **Day 24 — JSON**
- encoding/json package
- Marshal
- Unmarshal
- struct tags: json:"field_name"

---

## **Day 25 — Goroutines**
- lightweight threads
- go func() execution
- synchronization basics

---

## **Day 26 — Channels**
- unbuffered channels
- buffered channels
- send/receive syntax

---

## **Day 27 — Select & Concurrency Patterns**
- select statement
- closing channels
- worker pool pattern

---

## **Day 28 — Sync Package**
- sync.WaitGroup
- sync.Mutex
- avoiding race conditions

---

## **Day 29 — Testing**
- testing package
- writing unit tests
- table-driven tests
- benchmark tests

---

## **Day 30 — Final Mini Project**
A small working Go project combining:
- structs
- JSON
- file handling
- goroutines
- channels
- package structure

Suggested project ideas:
- Todo API
- Concurrent file downloader
- File-based user manager

---

# ✔ End of roadmap
This document fully covers all beginner and intermediate Go topics required to start building real applications.
