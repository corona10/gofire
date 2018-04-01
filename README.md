[![Build Status](https://travis-ci.org/corona10/fuego.svg?branch=master)](https://travis-ci.org/corona10/fuego)
[![GoDoc](https://godoc.org/github.com/corona10/fuego?status.svg)](https://godoc.org/github.com/corona10/fuego)
[![Go Report Card](https://goreportcard.com/badge/github.com/corona10/fuego)](https://goreportcard.com/report/github.com/corona10/fuego)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

# fuego
> Inspired by Google [python-fire](https://github.com/google/python-fire)

fuego is a library for automatically generating command line interfaces (CLIs) from function and struct.

## Features
* fuego is a simple way to create a CLI in Go.
* fuego helps with exploring existing code or turning other people's code into a CLI.

## Installation
```
go get github.com/corona10/fuego
```

## TODO
- Support flag options
- More error handling
- Support more types

[![asciicast](https://asciinema.org/a/173759.png)](https://asciinema.org/a/173759)

## [Examples](/_examples)

```go
package main

import (
	"fmt"

	"github.com/corona10/fuego"
)

type Sample struct {
	Name string
}

func (s Sample) Add(a, b int) int {
	return a + b
}

func (s Sample) Minus(a, b int) int {
	return a - b
}

func (s Sample) HelloWorld() {
	fmt.Println(s.Name)
	fmt.Println("Hello world!")
}

func main() {
	var s Sample
	s.Name = "test"
	fuego.Fire(s)
}
```

## Special thanks to
* [Haeun Kim](https://github.com/haeungun/)
