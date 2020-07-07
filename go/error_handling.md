Don't Just Check Errors, Handle Them Gracefully
-----------------------------------------------

There are 3 fundamental approaches to error handling in Go

**Sentinel Errors**
* if err == ErrSomething {...}, these are specific values used as a signal that an error did or did not occur.
* Least flexible error handling strategy.
* Never inspect the output of error.Error() - it is meant for human reading, not program inspection.
* Sentinel errors become part of your API. All implementations will be restricted to returning that error, even when
  something more descriptive could've been used.
* It also creates dependency between two different packages. You must import the other packages in order to check the value.
* *Avoid* these when possible.


**Error Types**
* A type that you create which implmements the Error interface.
* Also has the problem of coupling as with sentinel errors, because users need to import the package.
* *Avoid* these when possible.


**Opaque Errors**
* Just return the error without assuming anything about its contents.
* Assert errors for behavior, not type.
* github.com/pkg/errors (by Dave Cheney) can be helpful for error handling.
* Only handle errors *once*
* Annotating errors with errors.Wrap provides a clean way of handling once and providing context:
```
func Write(w io.Write, buf []byte) error {
	_, err := w.Write(buf)
	return errors.Wrap(err, "write failed")
}
```
*If you pass in nil, it will return nil*, you don't need to add the additional `if err != nil` piece.

**Summary**
* Errors are part of your package's public API.
* Treat errors as opaque; assert for behavior, not type.
* Minimize sentinel errors in your program.
* Convert externally receieved errors by wrapping them with errors.Wrap
* Use errors.Cause to recover the underlying error


Source [Don't just check errors, handle them gracefully | Dave Cheney](https://www.youtube.com/watch?v=lsBF58Q-DnY)
