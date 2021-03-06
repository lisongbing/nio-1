<p align="center">
<img src="https://raw.githubusercontent.com/go-nio/nio/master/nio-logo.png" width="160" />
</p>

<div align="center">
    
[![Build Status](https://travis-ci.org/go-nio/nio.svg?branch=master)](https://travis-ci.org/go-nio/nio)
[![codecov](https://codecov.io/gh/go-nio/nio/branch/master/graph/badge.svg)](https://codecov.io/gh/go-nio/nio) 
[![GoDoc](https://godoc.org/github.com/go-nio/nio?status.svg)](http://godoc.org/github.com/go-nio/nio) 
[![Go Report Card](https://goreportcard.com/badge/github.com/go-nio/nio)](https://goreportcard.com/report/github.com/go-nio/nio)

</div>

## Features

* <b>Zero</b> external runtime dependencies
* Smart HTTP Routing
* Data binding for JSON, XML and form payload
* Middlewares on global, group or single route level
* Full control of http server

### Builtin middlewares
* Basic Auth
* Body Dump
* Body Limit
* Compress (GZip)
* CORS
* CSRF
* Key Auth
* Method Override
* Recover
* Request ID
* Rewrite
* Secure
* Slash
* Static

## Getting Started

### Prerequisites

You need to have at least go 1.11 installed on you local machine.

### Installing

Install nio package with go get

```
go get -u github.com/go-nio/nio
```

Start your first awesome server. Create main.go file and add:
```go
package main

import (
    "net/http"
    "log"
    "github.com/go-nio/nio"
)

func main() {
	// Nio instance
	n := nio.New()

	// Routes
	n.GET("/", hello)

	// Start server
	log.Fatal(http.ListenAndServe(":1323", n))
}

// Handler
func hello(c nio.Context) error {
	return c.String(http.StatusOK, "Hello, World!")
}
```

And finally run it

```
go run main.go
```

## More examples

See [examples](https://github.com/go-nio/nio/tree/master/examples)

## Built With

* [Go](https://www.golang.org/)

## Contributing

Please read [CONTRIBUTING.md](https://github.com/go-nio/nio/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/go-nio/nio/tags). 

## Authors

* **Andzej Maciusovic** - *Initial work* - [anjmao](https://github.com/anjmao)

See also the list of [contributors](https://github.com/go-nio/nio/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details

## Acknowledgments

* This project is largely ispired by [echo](https://echo.labstack.com/). Parts of the code are adopted from echo. See NOTICE. 
