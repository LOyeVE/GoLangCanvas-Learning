# Golang(Go Programming Language)
## Install GoLang in Linux Systems
1.Go to [official website](https://golang.org/dl/) or [Chinese Forum](https://studygolang.com/dl) and download the latest version(i.e 1.11) of GoLang in archive file as follows:
```
$ cd ~/Downloads/
$ wget -c https://studygolang.com/dl/golang/go1.11.linux-amd64.tar.gz
```
2.Next,check the integrity of the tarball by verifying the SHA256 checksum of the archive file using the shasum command as below,where the flag `-a` is used to specify the algorithm to be used:
```
$ shasum -a go1.11.linux-amd64.tar.gz
```
**Important:** To show that the contents of the downloaded archive file are the exact copy provided on the GoLang website,the **256-bit** hash value generatede from the command above as seen in the output should be the same as that provided along with the download link.\n

if that is the case,proceed to the next step,otherwise download a new tarboll and run the check again.\n

3.Then extract the tar archive files into /usr/local directory using the command below:
```
$ sudo tar -C /usr/local -xvzf go1.11.linux-amd64.tar.gz
```
## Configuring GoLang Environment in Linux
4.First,setup your Go workspace by creating a directory `~/go_workspace` which is the root of your workspace.The workspace is made of three directories namely:  
-`bin` which will contain Go executable binaries.  
-`src` which will store your source files.  
-`pkg` which will store package objects.  
```
$ mkdir -p ~/go_workspace/{bin,src,pkg}
$ cd ~/go_workspace
$ ls
```
5.Now it`s time to execute Go like the rest of Linux programs without specifying its absolute path,its installation directory must be stored as one of the values of **$PATH environment variable**.
```
sudo vim /etc/profile
export PATH=$PATH:/usr/local/go/bin
source /etc/profile
```
6.Then,set the values of `GOPATH` and `GOBIN` go environment variables in your user profile file `~/.profile` or `~/bash_profile` to point to your workspace directory.
```
sudo vim /etc/profile
export GOPATH="$HOME/go_workspace"
export GOBIN="$GOPATH/bin"
source /etc/profile
```
## Verify GoLang Installation
8.Run the commands below to view your Go version and environment:
```
$ go version
$ go env
$ go help
```
## Complie and Run `Hello world,Golang!`
9.Begin by creating the hello project directory under ~/go_workspace/src/,
```
$ mkdir -p ~/go_workspace/src/hello
```
Then use your favorite enitor to create the *hello.go* file:
```
$ vi ~/go_workspace/src/hello/hello.go
```
And the lines below in the file,save it and exit:
```
package main
import "fmt"
func main() {
fmt.Printf("Hello,world.Golang")
}
```
10.Now,compile the program above as using go install and run it:
```
$ go install $GOPATH/src/hello/hello.go
$ $GOBIN/hello
```
---
**Reference Links**: https://golang.org/  
**Reference Links**: https://www.tecmint.com/install-go-in-linux/  
**Reference Links**: https://studygolang.com/  
