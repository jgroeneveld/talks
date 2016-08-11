## Go

<pre><code data-trim data-noescape>
type error interface {
    Error() string
}
</code></pre>

<pre><code data-trim data-noescape>
return 42, nil
return 0, errors.New("some error")
</code></pre>

<pre><code data-trim data-noescape>
answer, err := call_service()
if err != nil {
  panic(err)
}

doSomething(answer)
</code></pre>