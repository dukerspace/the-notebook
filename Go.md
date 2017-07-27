### Learning
- https://gobyexample.com

 ### install package
- go get

### Update your PATH environment variable
- export GOPATH=$HOME/go
- export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
- link: https://medium.com/@richardeng/in-the-beginning-61c7e63a3ea6

### Go routine
- ic_send_only := make (<-chan int)
 //a channel that can only send data - arrow going out is sending
- ic_recv_only := make (chan<- int)
//a channel that can only receive a data - arrow going in is receiving
