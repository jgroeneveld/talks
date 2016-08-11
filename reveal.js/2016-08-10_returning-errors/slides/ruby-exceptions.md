## Exceptions

<pre><code data-trim data-noescape>
class ApplicationError < StandardError; end
class InvalidError < ApplicationError
  # [...] 
end
</code></pre>

<pre><code data-trim data-noescape>
def call_service
  raise InvalidError, thing: 'foo' if fail?
  return 42
end
</code></pre>

<pre><code data-trim data-noescape>
answer = nil
begin
  answer = call_service
rescue InvalidError => e
  puts "invalid: #{e.thing}"
  return # or raise something again because this also failed
end
puts "hooray #{answer}"
</code></pre>

<pre><code data-trim data-noescape>
answer = call_service
</code></pre>

Notes:
- No need for propagation, but no communication to the developer that we are doing that
- Rails Exceptions, works for controllers but