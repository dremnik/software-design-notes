# Concurrency in Go


**Channels**
* Receivers always block until there is data to receive. If the channel is unbuffered,
  the sender blocks until the receiver has received the value. On the other hand, if the 
  channel has a buffer, the sender blocks until the value has been copied to the buffer.
  If the buffer is full, this means blocking until a receiver has received a value. [This
  feels like a pipeline to me]
* A buffered channel can be used like a semaphore (which is a variable that controls access
  to a shared resource), for instance to limit throughput. 

  ```
  var sem = make(chan int, MaxOutstanding)

  func Serve(queue chan *Request) {
	  for req := range queue {
		req := req // This is necessary because we don't want to share the iterator among routines
		sem <- 1
		go func() {
			process(req)
			<-sem
		}()
	  }
  }
  ```
  Once the MaxOutstanding number of handlers are executing process, each new call to handle
  in any new requests will block at `sem <- 1`, waiting for queue to drain to send a value
  into the channel. Once it's done, it will receive from the channel which opens it for sending from another handler.
  We have to shadow req in each iteration, which creates a fresh version of the variable, 
  because we don't want the goroutines having shared access to the for loops iteration variable.

  Another way of handling this issue is to create a fixed number of goroutines reading from
  the request channel

  ```
  func handle(queue chan *Request) {
	  for r := range queue {
		process(r)
	  }
  }

  func Serve(clientRequests chan *Request, quit chan bool) {
	  for i := 0; i < MaxOutstanding; i++ {
		go handle(clientRequests)
	  }
	  <-quit // Wait to be told to exit
  }
  ```


Concurrency made easy
---------------------

* If you have to wait for an operation, it's easier to do it yourself. Don't overuse goroutines
  when they aren't needed.
* Channels aren't resources like files or sockets, you don't need to close them to free them.
* Acquire semaphores when you're ready to use them, not when you expect to use it.
* Avoid mixing anon functions and goroutines - use named functions instead
* Before you start a goroutine, always know when, and how it will stop.
