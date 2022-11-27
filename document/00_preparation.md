**《go-new-knowledge》**  <code>Copyright©</code> 2022 [Tacks](https://github.com/Tacks9)

# 00 准备好一起进入 `GO` 语言的世界


- [00 准备好一起进入 `GO` 语言的世界](#00-%E5%87%86%E5%A4%87%E5%A5%BD%E4%B8%80%E8%B5%B7%E8%BF%9B%E5%85%A5-go-%E8%AF%AD%E8%A8%80%E7%9A%84%E4%B8%96%E7%95%8C)
  - [0. 引用](#0-%E5%BC%95%E7%94%A8)
  - [1. 什么是 `GO` 语言？](#1-%E4%BB%80%E4%B9%88%E6%98%AF-go-%E8%AF%AD%E8%A8%80)
    - [1.1 `GO` 的起源](#11-go-%E7%9A%84%E8%B5%B7%E6%BA%90)
    - [1.2 `GO` 的一些特性](#12-go-%E7%9A%84%E4%B8%80%E4%BA%9B%E7%89%B9%E6%80%A7)
  - [2. 环境](#2-%E7%8E%AF%E5%A2%83)
    - [2.1 我的环境](#21-%E6%88%91%E7%9A%84%E7%8E%AF%E5%A2%83)
    - [2.2 如何自定义环境变量](#22-%E5%A6%82%E4%BD%95%E8%87%AA%E5%AE%9A%E4%B9%89%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F)
  - [3. 如何编译 `GO` 语言](#3-%E5%A6%82%E4%BD%95%E7%BC%96%E8%AF%91-go-%E8%AF%AD%E8%A8%80)
    - [3.1 编译](#31-%E7%BC%96%E8%AF%91)
    - [3.2 Hello World](#32-hello-world)

## 0. 引用

- [Go Github](https://github.com/golang/go)
- [Go Downloads](https://golang.google.cn/dl/)


## 1. 什么是 `GO` 语言？

### 1.1 `GO` 的起源

`Go`（又称 `Golang`）是 `Google` 的 `Robert Griesemer`，`Rob Pike` 及 `Ken Thompson` 开发的一种静态强类型、编译型语言。起源于 2007 年，并在 2009 年正式对外发布，2012 年 1.0 版本推出，截止2022年11月，最新版本为 `v1.19.3`。 GO 和 C++、Java 和 C# 一样同属 C 系，吸收了不同语言的精髓于一身，把编译速度和执行速度达到某种最佳的平衡。目前越来越多的公司都开始引入 GO 语言来开发服务，尤其是云平台、分布式存储、服务端、网络编程等。

> 我们想要一个安全的、静态编译的、高性能的、类似`C++`和`Java`这样的语言，但是得更轻量级并且要像`Python`这种动态解释型语言这样有趣 （ by `Rob Pike`  Go语言项目总负责人）

- 目标：快速编译，高效执行，易于开发。


### 1.2 `GO` 的一些特性

> 如果你之前是用解释型语言工作，那么可能到编译型会觉得没有那么爽快，编译速度会让你觉得太慢了，但 `GO` 把快速编译作为目标之一， `import` 依赖管理包模型、语法的简练易解析等原因，让 `GO` 也有媲美解释型语言的快速编译。


- `GO` 是一门静态、强类型、编译型语言
    - 静态；数据类型在编译阶段检查，明确程序中变量类型，更可靠；而动态类型的语言如 `PHP`，则在运行时做类型检测;
    - 强类型；运行时不能改变变量类型，类型固定，不同类型不能直接运算；而弱语言类型如 `PHP`，在非同类型比较或运算，会做类型转换;
    - 编译型；将代码编译生成可执行文件，在编译期间可能捕获一些错误；而解释型语言如 `PHP` ，则无需编译直接解释器翻译进行；
- `GO` 具有垃圾回收机制 `Garbage Collection`
    - 在`C/C++`中 ，往往需要开发者自己管理内存防止泄露，例如 `free(val)` 等； `GO` 则提供 `GC` 机制，为开发者解决了这样令人头疼的内存释放工作，专注于业务；
    - 垃圾回收会增加一些额外的开销，但是也减少了一些致命性的 BUG ；
- `GO` 并发性 `Goroutine`
    - `Go` 语言从底层原生支持并发，无须第三方库，开发人员可以很轻松地在编写程序时决定怎么使用 `CPU` 资源;
- `GO` 面向对象
    - 没有类和继承的概念，而是采用接口 `interface` 来实现多态性；
- ...


## 2. 环境


### 2.1 我的环境

- `MAC M1 PRO`
- `Vscode 插件：Go v0.36.0`
- `Go version go1.18.4 darwin/arm64`

| 环境变量 | 作用  |
| :----: | :----:  |
| GOROOT | `go` 安装目录  |
| GOPATH | `go` 工作目录 （通常来说，会包含 `bin` 、`pkg` 、`src`） |
| GOPROXY| `go` 下载代理  |
| GO111MODULE | `go` 是否启用 `Modules`; 三种值，默认为 `auto`，启用可用`on` ，关闭可用`off` |

```shell
// Go 版本
$ go version
go version go1.18.4 darwin/arm64

// 强制设置 modules
$ go env -w GO111MODULE=on

// 设置代理
$ go env -w GOPROXY=https://goproxy.cn,direct

// 查看 GO 环境变量
$ go env | grep -E 'GOPATH|GOROOT|GOPROXY|GOARCH|GO111MODULE|GOVERSION|GCCGO'
GO111MODULE="on"
GOARCH="arm64"
GOPATH="/Users/Tacks9/go"
GOPROXY="https://goproxy.cn,direct"
GOROOT="/opt/homebrew/Cellar/go/1.18.4/libexec"
GOVERSION="go1.18.4"
GCCGO="gccgo"
```

### 2.2 如何自定义环境变量

```shell 
// 打开环境配置文件
$ vim ~/.bashrc
export GOROOT=/go安装目录
export PATH=$PATH:$GOROOT/bin go可执行目录
export GOPATH=/gopath目录

// 立即生效
$ source .bashrc
```

## 3. 如何编译 `GO` 语言

### 3.1 编译

`Go` 语言可以采用 `go build` 或者 `go run` 对代码进行编译，源代码文件后缀为 `.go` 。

- `go build` 可以将GO语言程序代码编译成二进制的可执行的文件，但是需要我们手动执行二进制文件来运行程序。
- `go run`   可以将GO语言编译后直接运行，在编译期间会产生一个临时文件，但是最后不会生成可执行文件，适合调试。

### 3.2 Hello World

- helloworld.go
```go
package main

import "fmt"

func main() {
	fmt.Println("hello world")
}
```

- go build 方式

```shell
$ go build helloworld.go 
$ ls
helloworld helloworld.go
$ ./helloworld
hello world
```

- go run 方式


```shell
$ go run helloworld.go 
hello world
```