# go-ternary

Ternary helper for Go programming language.<br />Helpful for anyone who always love to solve things in single line statement.

[![Go Report Card](https://goreportcard.com/badge/github.com/novalagung/go-ternary?no-cache=1)](https://goreportcard.com/report/github.com/novalagung/go-ternary)
[![Build Status](https://travis-ci.org/novalagung/go-ternary.svg?branch=master)](https://travis-ci.org/novalagung/go-ternary)
[![Coverage Status](https://coveralls.io/repos/github/novalagung/go-ternary/badge.svg?branch=master)](https://coveralls.io/github/novalagung/go-ternary?branch=master)

## Instalation

```bash
go get -u github.com/novalagung/go-ternary
```

## Usage

### Basic Example

```go
package main

import (
    . "github.com/novalagung/go-ternary"
)

func main() {
    left, right := 1, 1
    value := Ternary(left == right, "yes", "no").AsString()
    fmt.Println(value) // yes
}
```

### Other Example

```go
// example 1
Ternary(cond1 == cond2, float32(23.2), float64(44.21)).AsFloat32()

// example 2
Ternary(
    func () bool { return cond1 == cond2 },
    float32(23.2),
    float64(44.21),
).AsFloat32()

// example 3
Ternary(
    cond1 == cond2,
    func () []string { return arr },
    make([]string, 0),
).
ExecIfResultIsFunc().
AsInterface().
([]string)

// example 4
value := make([]string, 0)
Ternary(
    cond1 == cond2,
    func () []string { return arr },
    make([]string, 0),
).
ExecIfResultIsFunc().
StoreTo(&value)
```

## Documentation

- [godoc](https://godoc.org/github.com/novalagung/go-ternary)
- [pkg.go.dev](https://pkg.go.dev/github.com/novalagung/go-ternary)

## License

MIT License
