---
title: "DAX Editor más DAX Studio"
date: 2015-03-01T18:10:01+01:00

tags: ['DAX']
categories: ['DATOS']
author: "Geiber"
#noSummary: true

resizeImages: false
---
Los que han desarrollado un modelo tabular en SSAS han vivido lo complicado de administrar las medidas creadas en el grid del Model.bim. 

<!--more-->

{{< figure src="dax1.png">}}

Para ayudar en esta tarea han creado __Dax Editor__.  Una extensión para Visual Studio que te facilita administrar las medidas|cálculos que desarrollas. 

Una vez que has instalado esta extensión desde [*Visual Studio Extension Gallery*](https://visualstudiogallery.msdn.microsoft.com/356e3b3a-ccaa-4331-aec5-a446d8eefeaf)

{{< figure src="dax2.png" width="86%">}}

para sacarle proveche debería:

Desde el menú contextual de toolbars habilitar *DAX Editor*.

{{< figure src="dax3.png" width="86%">}}

Extraer el __Model.dax__ con la opción "Get Measures from BIM File" desde el menú MODEL

{{< figure src="dax4.png" width="86%">}}

Si los pasos se realizaron correctamente se debe observar la barra de herramientas del DAX Editor al tener seleccionado el archivo Model.dax

{{< figure src="dax5.png" width="36%">}}

Deberíamos incluir este archivo en el __*project solution*__

Esta extensión no te marca los paréntesis.  Si no tienes cuidado con los paréntesis al crear cálculos puedes generar errores.  Aquí es donde entra DAX Studio https://daxstudio.codeplex.com/.  Esta herramienta te facilita la edición de los cálculos con DAX, te marca donde abre y cierra paréntesis , nombres de  reservados, entre otras, y así evitamos generar bugs.  Simplemente edita tu archivo Model.dax con esta herramienta. 

{{< figure src="dax6.png" width="86%">}}

Puedes reincorporar tus medidas o ajustes al Model.bim utilizando la opción Save Measures to BIM File desde el toolbar o menú DAX

{{< figure src="dax7.png" width="86%">}}

