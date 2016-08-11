## Java

<pre><code data-trim data-noescape>
public void callService() throws ExceptionType1,
                 ExceptionType2, ExceptionType3
{
  throw new ExceptionType1();
}
</code></pre>
   
<pre><code data-trim data-noescape>
try
{
   callService()
}catch(ExceptionType1 e1)
{
   //Catch block
}catch(ExceptionType2 e2)
{
   //Catch block
}catch(ExceptionType3 e3)
{
   //Catch block
}
</code></pre>