
# Notas Programacion

Notas Generales sobre Programacion.





## Authors

- [@warshabcb](https://www.github.com/warshabcb)




## Documentation

### ConnectionStrings
``` json
"ConnectionStrings": {
    "DefaultConnection": "DataSource=app.db;Cache=Shared",
    "Linux": "server=IP;port=3306;database=Personas;user=USERNAME;password=PASSWORD"
  },
```


### Librerias Necesarias
``` Paquetes
Microsoft.EntityFrameworkCore
Microsoft.AspNetCore.Identity.EntityFrameworkCore
Microsoft.EntityFrameworkCore.Design
Microsoft.EntityFrameworkCore.SqlServer
Microsoft.EntityFrameworkCore.Tools
Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation
Microsoft.VisualStudio.Web.CodeGeneration.Design
Pomelo.EntityFrameworkCore.MySql
Microsoft.AspNetCore.Identity.UI
```

###
## Agregar Paquete
```
dotnet add package MySql.Data --version 8.3.0
```
```
dotnet add package Microsoft.EntityFrameworkCore --version 8.0.1
```
```
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore --version 8.0.1
```
```
dotnet add package Microsoft.EntityFrameworkCore.Design --version 8.0.1
```
```
dotnet add package Microsoft.EntityFrameworkCore.SqlServer --version 8.0.1
```
```
dotnet add package Microsoft.EntityFrameworkCore.Tools --version 8.0.1
```
```
dotnet add package Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation --version 8.0.1
```
```
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 8.0.0
```
```
dotnet add package Pomelo.EntityFrameworkCore.MySql --version 8.0.0-beta.2
```
```
dotnet add package Microsoft.AspNetCore.Identity.UI --version 8.0.1
```






### Configuraciones en Archivo Program
#### Acceso a Base Datos
```c#
//BaseDatos_MYSQL
var connectionString = builder.Configuration.GetConnectionString("Linux");
builder.Services.AddDbContext<Base_Datos>(options => options.UseMySql(connectionString, new MySqlServerVersion(new Version(8, 0, 11))));
```
Detectar Version Automaticamente
```
builder.Services.AddDbContext<Base_Datos>(options =>
    options.UseMySql(connectionString, ServerVersion.AutoDetect(connectionString)));
```
### Migraciones con Dotnet ef

#### Creacion Migracion
```
dotnet ef migrations add AjusteAspNetRoles
```
#### Eliminar Migracion
```
dotnet ef migrations remove  
```
#### Listar Migraciones
```
dotnet ef migrations remove  
```
#### Generar Script Migraciones
```
dotnet ef migrations script  
```

#### Actualizar a Base Datos
```
dotnet ef database update
```
#### Elimina la Base Datos
```
dotnet ef database drop
```
