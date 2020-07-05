7 Common Mistakes in Go and when to avoid them
------------------------------------------------

**1. Not accepting interfaces**
* Interfaces capture both state and behavior, two of the fundamental concepts in programming.
  They are one of the most powerful features of go, and they promote extensibility.
  Adherence is only satisfied by behavior.

* Instead of passing data structures through a method, pass an interface.


**2. Not using io.Reader and io.Writer**
* They are simple and flexible interfaces for many operations around input and output,
  and they provide access to a ton of functionality.
* This allows the code to be much more flexible in terms of the kind of operations a function can do
  if you pass an io.Reader or io.Writer interfaces through your functions/methods.


**3. Requiring Broad Interfaces**
* Interfaces are composable, and we can compose broader interfaces out of narrow ones.
* When passing interfaces through methods and functions, it is better to use a narrower interface to make 
  the code more extensible.


**4. Methods vs. Functions**
* Using too many methods. Methods are more specific than functions, which means they are therefore less extensible.
* The situation in which you would want to use a method is if you have to manipulate the state of the type, otherwise
  it is more likely that you want to use a function and interfaces being passed in.


**5. Pointers vs. Values**
* Generally *not* a question of *performance*, it is a question of *shared access*.
* If you want shared access, use a pointer. Otherwise, use values.
	- Pointer receivers are *not safe* for concurrent access, whereas values are.


**6. Thinking of errors as strings**
* Error is an *interface*!
* You can create custom errors:
  - to provide consistent context.
  - to provide a type which can be different from the error value
  - can provide dynamic values.


**7. Consider Concurrency**
* If you provide a library, someone will use it concurrently.
* Values aren't safe, you need to *create safe behavior* around them.
* Making it safe:
  * *Sync* package provides behavior to make a value safe
  * *Channels* coordinate values across goroutines by permitting one goroutine to acces at a time.


>Failure is a manifestation of learning and exploration. 
>If you aren't experiencing failure, then you are making a far worse mistake.
>You are being driven by the desire to avoid it. -Ed Catmull

Source: [7 Common Mistakes in Go by Steve Francia](https://www.youtube.com/watch?v=29LLRKIL_TI)
