multi line JSX expression should always be wrapped in parentheses. 

## Event listener
----
Event handler fn do not contain `()` when called on the event. ex
```JavaScript
return <div onHOver={handleHover}> </div>
```

if we added `()` to handleHover, would trigger the fn immediately instead of when the event happens.

