errgo
=====

Go Error Handling Package


Type err {
  code int
  time time.Now()
  msg  string
  next (ptr to next function to run)
}

// function to try running some function inside an infinite loop the length of which
// is determined by the *action function which will return true (next loop) or false (stop looping)
// if the loop exits

func (this *err) Try(func *fn(), func *action()) bool {}  // assign a value to err fields

// if no error was raised in the Try statement, run this one
func (this *err) Else(func *fn()) bool {}

// if the try failed and err.code != 200 (ok), run this function to catch the error
// and place corrective actions in this function
func (this *err) Except() error {}

// if the Except didn't fix the error, do final cleanup here and end the program
func (this *err) Finally() error {}
