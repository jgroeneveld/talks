##  Result Class

<pre><code data-trim data-noescape>
def call_service
  return Failure.new(:invalid, thing: 'foo') if fail?
  return Success.new(answer: 42)
end

result = call_service
result.on!(
  invalid: -> (thing:) { puts "invalid: #{thing}" },
  success: -> (answer:) { puts "hooray #{answer}" }
)

result = call_service
return result if result.failure?
</code></pre>

Notes:
- Clear interface,
- Convenience methods
- Clear Contract
- one object to pass around
- stacktrace possible