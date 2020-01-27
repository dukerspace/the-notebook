---
id: golang
title: Go Lang
type: docs
path: the-notebook/lang/golang
---

### Go Lang

#### Learning
- https://gobyexample.com

#### install package
- go get

#### Update your PATH environment variable
- export GOPATH=$HOME/go
- export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
- link: https://medium.com/@richardeng/in-the-beginning-61c7e63a3ea6

#### Go routine
- ic_send_only := make (<-chan int)
 //a channel that can only send data - arrow going out is sending
- ic_recv_only := make (chan<- int)
//a channel that can only receive a data - arrow going in is receiving

#### Pointer

& ส่ง
* รับ

```
package main

import "fmt"

type human struct {
	name    string
	age     int
	isAdult bool
}

// ใช้ * แทนการ dereference หรือการถอดเอาค่าที่แท้จริงออกมา
func setAdult(h *human) {
	h.isAdult = h.age >= 18
}

func main() {
	somchai := human{name: "Somchai", age: 23}
    // ใช้ & แทนการอ้างถึง reference
	setAdult(&somchai)
	fmt.Println(somchai) // {Somchai 23 true}
}
```

[reference](https://www.babelcoder.com/blog/posts/intro-to-golang)

#### Private and Public Visibility
- private Lowwer case -> func a()
- public Upper case  => func A()
