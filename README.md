# CS_CreacionDeAplicacionesE3

1. En el archivo **DotNetDependencies.csproj**
, observe `dependencies`
. Debería ser similar a este código

```xml
<ItemGroup>
    <PackageReference Include="Humanizer" Version="2.7.9" />
</ItemGroup>
```

1. Para ver las dependencias instaladas, ejecute este comando:

```xml
dotnet list package
```

Esto debería generar la versión solicitada y la versión final resuelta (es decir, instalada).

Top-level Package      Requested   Resolved
> Humanizer            2.7.9        2.7.9

1. Para ver qué dependencias están obsoletas, ejecute este comando:

```xml
dotnet list package --outdated
```

La salida debería ser similar a la siguiente. Es posible que vea otros valores en la columna `Latest`

```
DotNetDependencies
```

Project

has the following updates to its packages
[net6.0]:
Top-level Package      Requested   Resolved   Latest
> Humanizer            2.7.9       2.7.9      2.11.10

De forma predeterminada, este comando buscará la última versión estable. Para buscar paquetes de versión preliminar, anexe `--include-prerelease`
 al comando anterior:

```bash
dotnet list package --outdated --include-prerelease
```

1. Puede actualizar a la versión `Latest`
, con cierto nivel de confianza. De este modo, se asegurará de que las dependencias obtengan las características y revisiones más recientes de esa versión principal. Para instalar la versión más reciente, ejecute el siguiente comando:

```bash
dotnet add package Humanizer
```

La salida debe ser similar a esta:

```xml
info : PackageReference for package 'Humanizer' version '2.11.10' updated in file 'C:\Users\username\Desktop\DotNetDependencies\DotNetDependencies.csproj'.
```

En la salida se indica que las dependencias del proyecto se han actualizado.

Si quiere actualizar a una versión específica de la dependencia, puede anexar el parámetro `--version` e indicar la versión concreta.

```bash
dotnet add package Humanizer --version 2.11.10
```

Por último, también puede instalar el paquete de versión preliminar más reciente. Para ello, anexe el parámetro `--prerelease`

```bash
dotnet add package Humanizer --prerelease
```

Es posible que los resultados sean ligeramente distintos. La versión indicada debe corresponderse con la última versión disponible del paquete.
