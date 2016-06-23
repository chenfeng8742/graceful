## Package information

Enables graceful shutdown for the [Iris web framework](https://github.com/kataras/iris).

## Usage

```go
package main

import (
    "github.com/iris-contrib/graceful"
    "github.com/kataras/iris"
    "time"
)

func main() {
    api := iris.New()
    api.Get("/", func(c *iris.Context) {
        c.Write("Welcome to the home page!")
    })

    graceful.Run(":3001", time.Duration(10)*time.Second, api)
}

```
