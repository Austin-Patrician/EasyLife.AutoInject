###  What is this?
- <a href="https://www.nuget.org/packages/EasyLife.AutoInject.Attributes" target="blank">Nuget Address</a>


- It help us to easy DI by SourceGenerator.
- The AutoInject Attributes support three DI lifetime. And the default lifetime is 'ServiceLifetime.Scoped'.
- If you care about the Reflection performance gap, then you supposed to use this!!!
###  How to use?
  ```
  dotnet add package EasyLife.AutoInject.Attributes --version 1.0.0
     dotnet add package EasyLife.AutoInject --version 1.0.4
  ```
     
### Example
  ```
   - 2.1
   [AutoInject<IJwtService>]
   public class JwtService : IJwtService
   Equal -> builder.services.AddScoped<IJwtService,JwtService>();

   - 2.2
   [AutoInject<IGoodsManager>(ServiceLifetime.Transient)]
   public class GoodsManager : IGoodsManager
   Equal -> builder.services.AddTransient<IGoodsManager,GoodsManager>();

   - 2.3
   [AutoInject]
   public class TestService2 : ITest2Service
   Equal -> builder.services.AddScoped<TestService2>();

- 3. Then add the static extension method to the program.cs. 
   builder.Services.AddAutoInject();
```

### Extra

- Using the above steps then you can finish the Auto DI by SourceGenerator.
- If you are interested in how,  may be you can open the folder user the Dependencies / .Net Version your local /  Source Generators ,then will find it will generate some code we wanted.

