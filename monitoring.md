## Monitoring
### When to write a log
If is a branch that stops the normal flow code then log a warning

Before:
```csharp
if (entity == null)
{
    return null;
}

```
After:
```csharp
if (entity == null)
{
    _logger.LogWarning("Entity with id {Id} is not found", id)
    return null;
}
```

If is a normal branch and there is a remarkable event then log a information:

```csharp
_logger.LogInformation("An entity has been created")
```