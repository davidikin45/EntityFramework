# Entity Framework

 ## Reverse Engineer Db Context
* https://docs.microsoft.com/en-us/ef/core/get-started/aspnetcore/existing-db
* https://www.learnentityframeworkcore.com/walkthroughs/existing-database

Create Model
```
dotnet ef dbcontext scaffold "Server=.\;Database=AdventureWorksLT2012;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -o Model -c "AdventureContext"

dotnet ef dbcontext scaffold "Server=.\;Database=AdventureWorksLT2012;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -c "AdventureContext" -d 

Scaffold-DbContext "Server=.\;Database=AdventureWorksLT2012;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Model -Context "AdventureContext" -DataAnnotations
```

Specifying Tables
```
dotnet ef dbcontext scaffold "Server=.;Database=WideWorldImporters;Integrated Security=true;" Microsoft.EntityFrameworkCore.SqlServer -c WorldWideContext -o Data -t Sales.Orders -t Sales.OrderLines
```

Specifying Schema
```
dotnet ef dbcontext scaffold "Server=.;Database=WideWorldImporters;Integrated Security=true;" Microsoft.EntityFrameworkCore.SqlServer -c WorldWideContext -o Data --schema Purchasing
```

Updating the Model
```
dotnet ef dbcontext scaffold "Server=.\;Database=AdventureWorksLT2012;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -c "AdventureContext" -force

Scaffold-DbContext "Server=.\;Database=AdventureWorksLT2012;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Model -Context "AdventureContext" -Force
```