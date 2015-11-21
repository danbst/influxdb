# Background

The goal of this guide is to capture some Do and Don'ts of Go code for the InfluxDB database. When it comes to Go, writing good code is often achieved with the help of tools like `go fmt` and `go vet`. However there are still some practices not enforceable any any tools. This guide lists some specific practices to follow when writing code for the database.

*Like everything, one needs to use good judgment.* There will always be times when it doesn't make sense to follow a guideline outlined in this document. If that case arises, be ready to justify your choices.

# The Guidelines

## Try not to use third-party libaries

A third-party package is defined as one that is not part of the standard Go distribution. Generally speaking we prefer to minimize our use of third-party packages, and avoid them unless absolutely necessarily. We'll often write a little bit of code rather than pull in a third-party package. Of course, we do use some third-party packages -- most importantly we use [BoltDB](https://github.com/boltdb/bolt) in some storage engines. So to maximise the chance your change will be accepted by us, use only the standard libraries, or the third-party packages we have decided to use.

For rationale, check out the post [The Case Against Third Party Libraries](http://blog.gopheracademy.com/advent-2014/case-against-3pl/).

## Always include a default case in a 'switch' statement

## When -- and when not -- set a channel to 'nil'

## Use defer with anonymous functions to handle complex locking

## When to call 'panic()'

# Useful links
- [Useful techniques in Go](http://arslan.io/ten-useful-techniques-in-go)
- [Go in production](http://peter.bourgon.org/go-in-production/)
- [Principles of designing Go APIs with channels](https://inconshreveable.com/07-08-2014/principles-of-designing-go-apis-with-channels/)
- [Common mistakes in Golang](http://soryy.com/blog/2014/common-mistakes-with-go-lang/). Especially this section `Loops, Closures, and Local Variables`

