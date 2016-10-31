## Package information

This is a highly edited project (in order to make it work with Iris), original project is located [here](https://github.com/tylerb/graceful).

Enables graceful shutdown for the [Iris web framework v4](https://github.com/kataras/iris/tree/4.0.0).

## Instalation

```sh $ go get gopkg.in/iris-contrib/graceful.v4 ```

## Usage

```go
package main

import (
    "gopkg.in/iris-contrib/graceful.v4"
    "gopkg.in/kataras/iris.v4"
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
