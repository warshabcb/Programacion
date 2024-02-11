
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


### Configuraciones en Archivo Program
#### Acceso a Base Datos
```c#
//BaseDatos_MYSQL
var connectionString = builder.Configuration.GetConnectionString("Linux");
builder.Services.AddDbContext<Base_Datos>(options => options.UseMySql(connectionString, new MySqlServerVersion(new Version(8, 0, 11))));
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
