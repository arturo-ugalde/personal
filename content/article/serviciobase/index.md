---
title: "Fundamentos de un servicio"
date: 2020-09-13

tags: ['Microservicio', '.Net Core', 'Docker']
categories: ['Web', 'Backend']
author: "Geiber"
#noSummary: true

resizeImages: false
---

La implementación de servicios Web es una tarea que puede realizarse utilizando ASP.Net Core.  Este framework permite implementar servicios muy elaborados y agnosticos de una plataforma, sin embargo es importante conocer los fundamentos para ir a código más avanzado. 

<!--more-->

Primero vamos a listar los pasos que podemos realizar para conocer los fundamentos de un servicio.

* Utilizar una plantilla de asp.net core.
* Habilitar la contenerización en el servicio.
* Permitir correr como un Windows Service.

La instrucción siguiente crea un nuevo proyecto Web con las características básicas para correr en el puerto 5000.
{{< highlight html >}}
  dotnet new web -out servicio
{{< / highlight >}}

Podemos iniciar el servicio como sigue:
{{< highlight html >}}
    dotnet run servicio
{{< / highlight >}}

Utilizando curl, fiddler, postman o un navegador podemos hacer GET al servicio:

{{< highlight html >}}
    C:\>curl http://localhost:5000
    Hello World!
    C:\>
{{< / highlight >}}

Otros de los fundamentos de una servicio es habilitar la contenerización que nos permitirá hospedarlo en un servicio en la nube como AWS, Azure o nuestro propio Docker. [Aquí](https://docs.docker.com/engine/examples/dotnetcore/) encontramos información para dockerizar nuestra aplicación configurando un Dockerfile en el proyecto.

{{< highlight docker >}}
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build-env
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet", "servicio.dll"]
{{< / highlight >}}

Con este Dockerfile podemos crear la imagen y correr la aplicación en Docker Desktop utilizando las siguientes instrucciones:

{{< highlight html >}}
    docker build -t servicio .
    docker run -d -p 8080:80 --name servicio1 servicio
{{< / highlight >}}

Para así poder consumir el servicio desde un contenedor como sigue:
{{< highlight html >}}
    C:\>curl http://localhost:8080
    Hello World!
    C:\>
{{< / highlight >}}

Por último es útil saber que existen múltiples extensiones que permite elaborar más el servicio Web. Una de estas extensiones es __Microsoft.Extensions.Hosting.WindowsServices__, la cual habilita el servicio a ser hospedado y correr como un Windows Servicio.

En el siguiente video muestro como funciona estas instrucciones y opciones fundamentales:

{{< youtube JAvStKhbOQ0 >}}




