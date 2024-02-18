
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

## Algunas Herramientas
```
dotnet tool install --global dotnet-aspnet-codegenerator
```
## Crear controlador con Codigo Terminal
Se debe de cambiar el NameSpace Manualmente
```
dotnet aspnet-codegenerator controller -name FisicosController -outDir Controllers
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

#### Insertar Usuario Script
```
INSERT INTO `AspNetUsers` (`Id`, `Discriminator`, `Nombre`, `PrimerApellido`, `SegundoApellido`, `Telefono`, `Estado`, `UserName`, `NormalizedUserName`, `Email`, `NormalizedEmail`, `EmailConfirmed`, `PasswordHash`, `SecurityStamp`, `ConcurrencyStamp`, `PhoneNumber`, `PhoneNumberConfirmed`, `TwoFactorEnabled`, `LockoutEnd`, `LockoutEnabled`, `AccessFailedCount`) VALUES
('463b50c7-ede6-4b5c-84ca-3e8de342bd1e', 'Usuario', 'Warshab', 'Contreras', 'Bustos', '+50687187484', 0, 'warshab.contreras@gmail.com', 'WARSHAB.CONTRERAS@GMAIL.COM', 'warshab.contreras@gmail.com', 'WARSHAB.CONTRERAS@GMAIL.COM', 0, 'AQAAAAIAAYagAAAAEN7ZSJIwebjAiqvt4n6+EoslmorUc9iFeS4FT3425+fbvx8UwXlgyHsT0Y73kdZ4eQ==', 'YJAET2KJUFYXYZFTT54EKFAXVM3BYRKT', 'b21823f1-705a-4c76-9251-0d96fd8891e8', NULL, 0, 0, NULL, 1, 0);
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

## MVC Notas 

#### Definir el Layout a Utilizar
```
@{
    Layout = "~/Views/Shared/_MiLayout.cshtml";
}
```
or
```
public ActionResult MiAccion()
{
    return View("MiVista", "_MiLayout");
}
```

##  Agregar Ultima Version Boostrap
### Comando Terminal
```
dotnet add package bootstrap --version 5.3.2
```

