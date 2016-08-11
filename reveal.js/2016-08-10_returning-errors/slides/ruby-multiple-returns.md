## Multiple Returns

<pre><code data-trim data-noescape>
def call_service
  return :invalid, Args.new(thing: 'foo') if fail?
  return :success, Args.new(answer: 42)
end
</code></pre>

<pre><code data-trim data-noescape>
result, args = call_service
case result
when :invalid
  puts "invalid: #{args.thing}"
when :success
  puts "hooray #{args.answer}"
else
  raise 'unhandled'
end
</code></pre>

<pre><code data-trim data-noescape>
result, args = call_service
return result, args if result != :success
</code></pre>

Notes:
- Can not use hash as args, might cause propagation of nil
- Testing not super easy