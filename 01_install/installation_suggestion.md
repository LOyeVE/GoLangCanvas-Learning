#Golang(Go Programming Language)#
##Install GoLang in Linux Systems##
1.Go to [official website](https://golang.org/dl/) or [Chinese Forum](https://studygolang.com/dl) and download the latest version(i.e 1.11) of GoLang in archive file as follows:
```
$ cd ~/Downloads/
$ wget -c https://studygolang.com/dl/golang/go1.11.linux-amd64.tar.gz
```

2.Next,check the integrity of the tarball by verifying the SHA256 checksum of the archive file using the shasum command as below,where the flag `-a` is used to specify the algorithm to be used:
```
$ shasum -a go1.11.linux-amd64.tar.gz
```
**Important:**To show that the contents of the downloaded archive file are the exact copy provided on the GoLang website,the **256-bit** hash value generatede from the command above as seen in the output should be the same as that provided along with the download link.

if that is the case,proceed to the next step,otherwise download a new tarboll and run the check again.

3.Then extract the tar archive files into /usr/local directory using the command below:
```
$ sudo tar -C /usr/local -xvzf go1.11.linux-amd64.tar.gz
```

##Configuring GoLang Environment in Linux##

https://www.tecmint.com/install-go-in-linux/
