## Package information

This is a highly edited project (in order to make it work with Iris), original project is located [here](https://github.com/tylerb/graceful).

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
