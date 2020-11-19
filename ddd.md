# Domain Driven Design
## Avoiding mutation

We have to avoid mutations, we have to use encapsulation to protect our domain state from changes made to other services without checking business rules.

### Use readonly properties

Instead of:
```csharp
public string Name { get; set; }
```

Use:
```csharp
// The property is initialized in the constructor
public string Name { get; }

// In C#9 we can use init
public string Name { get; init; }
```

## Rich vs Anemic domain model

We have to avoid classes void of behavior in domain models. 

https://martinfowler.com/bliki/AnemicDomainModel.html

