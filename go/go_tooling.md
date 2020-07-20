# Go Tooling

`go test -coverprofile filename.cp` -> `go tool cover -html=filename.cp`
* gives a representation of the current testing coverage in the code.

**go-wrk**
* allows you to do load testing for a server

**go tool pprof**
* profiling for code to see which calls are spending the most time.

**go-torch**
* flamegraph for go. gives a visual representation of the call stack.

**benchmarking**
* used in similar way to tests, except provides performance benchmarks.
