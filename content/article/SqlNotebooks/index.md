---
title: "SQL Notebooks (VSCode vs Azure Data Studio)"
date: 2020-09-06

tags: ['Notebooks', 'SQL', 'Python']
categories: ['DATOS']
author: "Geiber"
#noSummary: true

resizeImages: false
---
A continuación quiero presentar el resultado de comparar dos alternativas para utilizar *Notebooks* con SQL Server: __Jupyter notebooks en VSCode__ versus __notebooks en Azure Data Studio__.  Estas herramientas resultan útiles para el análisis de datos y son alternativas al SQL Management Studio (*común entre desarrolladores*).

<!--more-->


## Configurar Jupyter Notebooks en Visual Studio Code

 Asumiremos que tienes instalado un *engine de Python* en su equipo (e.g. [*Anaconda*](https://docs.anaconda.com/anaconda/install/windows/) o [*MiniConda*](https://docs.conda.io/en/latest/miniconda.html)).

Por lo tanto iniciamos instalando la extensión de Python (__View>Extensions__) como se muestra en la siguiente figura:
{{< figure src="Extension.png">}}

Posteriormente se debe seleccionar el interprete o ambiente de Python (__View>Command Palette>*Python: Select Interpreter*__)
{{< figure src="Interpreter.png">}}{{< figure src="python.png">}}

En la barra de estado del VSCode aparecerá la versión de Python a utilizar: *(Python 3.7.6 64-bit('base':conda))*

Luego para crear el Notebook podemos utilizar el *Command Palette* nuevamente y digitar *"__>Python: Create New Blank Jupyter Notebook__"*:
{{< figure src="JupyterNotebook.png">}}

En VSCode se creará un archivo extensión __ipynb__ donde empezaremos a configurar la conexión al SQLServer:

{{< figure src="notebook.png">}}

Dos librería son indispensables para configurar el notebook: __ipython-sql__ y __pyodbc__; para instalarlos en nuestro ambiente podemos utilizar una celda de código del notebook con las siguientes instrucciones:

{{< figure src="runpip.png">}}

{{< highlight notebook>}}
!pip install ipython-sql
!pip install pyodbc
{{< /highlight >}} 


Seguidamente habilitamos el módulo de SQL con la instrucción: 
{{< highlight notebook>}}
%load_ext sql
{{< /highlight >}} 

Sólo hace falta conectarnos a nuestro servidor con un string de conexión de formato [SqlAchemy](https://docs.sqlalchemy.org/en/13/dialects/mssql.html#connecting-to-pyodbc) que tiene la siguiente forma para una conexión tipo __Windows Authentication__:
{{< highlight notebook>}}
mssql+pyodbc://NOMBRESERVIDORBD/NOMBREBASEDATOS?driver=ODBC+Driver+13+for+SQL+Server&trusted_connection=yes
{{< /highlight >}} 

Con la conexión establecida podemos utilizar __*%%sql*__ para hacer un query multilinea o __*%sql*__ en una sóla línea de la siguiente manera:

{{< highlight python>}}
%sql SELECT top 5 *  FROM [AdventureWorksDW2016].[dbo].[FactInternetSales]
{{< /highlight >}} 

Multilinea: 
{{< highlight python>}}
%%sql
SELECT TOP (1000) [ProductKey]
      ,[OrderDateKey]
      ,[DueDateKey]
      ,[ShipDateKey]
      ,[CustomerKey]
      ,[PromotionKey]
      ,[CurrencyKey]
      ,[SalesTerritoryKey]
      ,[SalesOrderNumber]
      ,[SalesOrderLineNumber]
      ,[RevisionNumber]
      ,[OrderQuantity]
      ,[UnitPrice]
  FROM [AdventureWorksDW2016].[dbo].[FactInternetSales]
{{< /highlight >}} 

El notebook utilizado lo encontramos en:
{{< gist arturo-ugalde 6cf4e3db89f5c3a384637feccdbc4dc5 "sqlNotebook.ipynb" >}}

Ahora haremos los mismo con __Azure Data Studio__.

## SQL Notebooks con Azure Data Studio

En apariencia Azure Data Studio simplifica la configuración de la librerías Python para VSCode, sólo vamos a __File>New Notebook__ para crear el notebook con la misma extensión __ipynb__:

{{< figure src="ADSNotebook.png">}}

Luego de crear el notebook necesitaremos crear una conexión al servidor.

{{< figure src="ADSConnect.png" width="66%">}}

Y agregammos las mismas consultas que hicimos anteriormente:

{{< figure src="ADS.png">}}

### *Hastas aquí todo parece más fácil con Azure Data Studio...*

En el siguiente video veremos diferencias entre ambas herramientas:

{{< youtube ctiOLdIwBcM >}}
