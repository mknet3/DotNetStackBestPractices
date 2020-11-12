# Performance
## Use async/await whenever possible
Life is async, and our code should be async as well. **Why would we want to block the thread instead of using async pattern?**

## Avoid blocking threads
`sometask.Wait()`, `sometask.Result`, `sometask.GetAwaiter().GetResult()` are evil methods and should be avoided as a general rule.