# APIs capable of scale in Go

**Basic project structure**
```
myapp/
	server.go
	routes.go
	handle_something.go
	handle_something_test.go
	handle_something_else.go
	handle_something_else_test.go
	cmd/
		myapp/
			main.go
```
* Put all routes in routes.go

Make a server struct:
```
type Server struct {
	database *db.Conn
	logger Logger
	email MailSender
	router *mux.Router
	// You get the point
}
``` 
which will hold the shared dependencies (because there will be multiple servers behind a load balancer).

**Helpers for responding**

```
func (s *Server) Respond(w http.ResponseWriter, r *http.Request, data interface{}, status int)
```

**Helpers for decoding**
```
func (s *Server) Decode(r *http.Request, v interface{}) error {
	return json.NewDecoder(r.Body).Decode(v) // maybe
}
```

**Error handler**
```
type errorHandler struct {
	err error
	status int
}

func (e errorHandler) ServeHTTP(w http.ResponseWriter, r *http.Request) {
	http.Error(w, e.err.Error(), e.status)
}
```

Server should *implement* http.Handler

```
func (s *Server) ServeHTTP(w http.ResponseWriter, r *http.Request) {
	s.Router.ServeHTTP(w, r)
}
```

