Focus on Python over Golang

<details>
<summary>GOPATH vs GOROOT</summary>

Installing Golang via Homebrew automatically generates two directories critical to running Go:
- `GOROOT` ( /usr/local/go ): 
    
    The Go "root" directory contains <ins> **Go's source code**</ins>. Homebrew will automatically register this path for you; there's little reason to mess around in here unless you're a Go contributor or if you're attempting to run multiple versions of Go.
- `GOPATH` ( /Users/toddbirchard/go ): 
    
    Unlike most programming languages, Go takes an opinionated stance that <ins> **all projects** </ins>  and dependencies of the language <ins> **should exist in a single directory known as the GOPATH**</ins> . Any time we develop a Go project or install a third-party module, the actions taken ultimately happen inside this directory
    
</details>

---
<details>
<summary>Go Packages</summary>

- Go programs are made up of "packages," which mirror packaging concepts in other programming languages (think modules in Python or packages in Java). 

- Every Golang program contains a **package called**  `main`, which serves as the project's entry point.


To make the package available to other apps, we need to install corresponding package in to `go runtime`
```
cd <package_name>
go install
```
- It will be stored in `User/ayush/go/pkg/<os_type>/<project_name>`
- For mac, os_type is `darwin_amd64`
    - `<package_name>.a` file is generated | Compiled package, linkable
    - The package is now avaible in `main.go`

---

</details>
<details>
<summary>Go Modules [third-party libraries]</summary>

Go modules are third-party libraries installed by Go. Modules are essentially projects which have been published for general use as dependencies in your projects.

</details>
<details>
<summary>Go Vendors</summary>

While modules can be installed to the `/pkg/mod` directory for global use, **source projects** can contain their **own versions of these modules to avoid clashing dependency** versions between projects (**similar to Python virtual environments**). While not required, you can choose to keep module versions project-specific (we will do this in our example).
</details>

---
<details>
<summary>Setup</summary>

#### Add GOPATH to your PATH
```
vim ~/.zshrc
export GOPATH=/Users/ayush/go
export PATH=$PATH:$GOPATH
export PATH=$PATH:$GOPATH/bin
source ~/.zshrc
sudo chmod 777 /bin/goimports
```
- Copy project from `/usr/local/go/src` to `/Users/ayush/go/src/`
### Change VS Code Settings
```
"go.gopath": "/Users/ayush/go",
"go.toolsGopath": "/Users/ayush/go",
```
- Clone project in the `User/ayush/go/src`
#### Initialize our project as a Go module
```
go mod init github.com/aroraayush/golang-data-structures
```
#### Output
`go: creating new go.mod: module github.com/aroraayush/golang-data-structures`
- A new file will appear in your directory called `go.mod`
    - `go.mod` contains information about our module for others, such as the module name and Go version it is intended for

</details>

---
Go is a compiled language, we need to build our project before we can run it 
```
go build
go run main.go
```
<details>
<summary>Code Formatting</summary>
```
go fmt
```
</details>

---
Do `go run <filename>` in each directory

---
> Primitives
-
