# Clean Code in C#

## Don't forget SOLID / DRY / KISS

## Avoid regions
Why we use regions? The use of regions is an antipattern and should be avoid in most of the cases. Using regions is a symptom of large classes with different responsabilities (Single Responsability Principle of SOLID).

https://softwareengineering.stackexchange.com/questions/53086/are-regions-an-antipattern-or-code-smell

## Avoid large and complex Startup classes
It is better to organize Dependency Injection configuration in features. For example we can have classes to configure MVC, Swagger, HealthChecks, ApplicationServices...

This can be done with extension methods:

Before
```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddControllers();
    services.AddAuthorization();
    services.AddAuthentication().AddOpenIdConnect();
    services.AddScoped<IFooRepository, FooRepository>();
    services.AddScoped<IBarRepository, FooServiceFoo>();
    services.AddScoped<IFooService, ServiceFoo>();
    services.AddScoped<IBarService, ServiceBar>();
}
```

After
```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddControllers();
    services.AddAuthorization();
    services.AddAuthentication().AddOpenIdConnect();
    services.AddApplicationServices();
}
```
```csharp
public static class ApplicationConfiguration 
{
    public static AddApplicationServices(this IServiceCollection services)
    {
        services.AddScoped<IFooRepository, FooRepository>();
        services.AddScoped<IBarRepository, FooServiceFoo>();
        services.AddScoped<IFooService, ServiceFoo>();
        services.AddScoped<IBarService, ServiceBar>();
    }
}
```

## Avoid logic in controllers

https://makingloops.com/fat-controller-causes/