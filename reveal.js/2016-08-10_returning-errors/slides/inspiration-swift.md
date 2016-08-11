## Swift

<pre><code data-trim data-noescape>
enum Result<T> {
    case Success(T)
    case Failure(String)
}
</code></pre>

<pre><code data-trim data-noescape>
return Result.Failure("some error")
return Result.Success("thing")
</code></pre>

<pre><code data-trim data-noescape>
var result = call_service()

switch result {
case Success(let thing):
    doSomethingWithResult(thing)
case Failure(let errString):
    println(errString)
}
</code></pre>