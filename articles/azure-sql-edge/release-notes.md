---
title: Notas de la versión de Azure SQL Edge
description: Notas de la versión en las que se detallan las novedades y los cambios en las imágenes de Azure SQL Edge
keywords: notas de la versión SQL Server
services: sql-edge
ms.service: sql-edge
ms.topic: conceptual
ms.subservice: ''
author: VasiyaKrishnan
ms.author: vakrishn
ms.reviewer: sstein
ms.date: 11/24/2020
ms.openlocfilehash: bb0c176ee8c145e1268827d79b453628e6f1bc28
ms.sourcegitcommit: 6a770fc07237f02bea8cc463f3d8cc5c246d7c65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95808621"
---
# <a name="azure-sql-edge-release-notes"></a>Notas de la versión de Azure SQL Edge 

En este artículo se describen las novedades y los cambios en cada nueva compilación de Azure SQL Edge.

## <a name="azure-sql-edge---101"></a>Azure SQL Edge: 1.0.1

### <a name="sql-engine-build-number---15020001553"></a>Número de compilación del motor SQL: 15.0.2000.1553

### <a name="whats-new"></a>Novedades

- Permitir la expresión Datebucket definida en columnas calculadas

### <a name="fixes"></a>Correcciones

- Corrección de la directiva de retención para quitar la tabla con la directiva de retención habilitada con tiempo de espera infinito
- Compatibilidad con la implementación de DacFx para las características de la directiva de retención y transmisión 
- Corrección de implementación de DacFx para habilitar la implementación desde la carpeta anidada en la dirección URL de SAS 
- Corrección de PREDICT para admitir nombres de columna largos en mensajes de error

## <a name="azure-sql-edge---100-rtm"></a>Azure SQL Edge: 1.0.0 (RTM)

### <a name="sql-engine-build-number---15020001552"></a>Número de compilación del motor SQL: 15.0.2000.1552

### <a name="whats-new"></a>Novedades
1. Imágenes de contenedor basadas en Ubuntu 18.04. 
2. Compatibilidad con la sintaxis de `IGNORE NULL` y `RESPECT NULL` con funciones `LAST_VALUE()` y `FIRST_VALUE()`. 
3. Mejoras de confiabilidad de PREDICT con ONNX.
4. Compatibilidad con la limpieza basada en directivas de retención de datos.
   - Compatibilidad del búfer en anillo con la tarea de limpieza de la retención para la solución de problemas.
5. Compatibilidad de nuevas características 
   - Recuperación rápida
   - Optimización automática de consultas
   - Habilitación de escenarios de ejecución en paralelo
6. Mejoras de ahorro de energía en modo de bajo consumo
7. Compatibilidad con streaming de nuevas características 
   - [Ventanas de instantánea](/stream-analytics-query/snapshot-window-azure-stream-analytics): nuevo tipo de ventana que permite agrupar por los eventos que llegan exactamente a la misma hora. 
   - Habilite [TopOne](/stream-analytics-query/topone-azure-stream-analytics) y [CollectTop](/stream-analytics-query/collecttop-azure-stream-analytics) como función analítica; de esta forma, se devolverán los registros ordenados por la columna de su elección, sin necesidad de ser parte de una ventana. 
   - Mejoras a [MATCH_RECOGNIZE](/stream-analytics-query/match-recognize-stream-analytics). 

### <a name="fixes"></a>Correcciones
1. Mensajes de error adicionales y detalles para solucionar problemas de operaciones de streaming de TSQL. 
2. Mejoras para conservar la duración de la batería en modo inactivo. 
3. Correcciones del motor de streaming de TSQL: 
   - Limpieza del trabajo de streaming detenido 
   - Correcciones de mejoras en la localización y el control de Unicode
   - Mejora de la capacidad de depuración de streaming de TSQL para Edge, que permite a los usuarios consultar errores de los trabajos desde get_streaming_job.
4. Limpieza basada en directivas de retención de datos
   - Correcciones para escenarios de creación y limpieza de directivas de retención.
5. Correcciones en tareas de temporizador en segundo plano para mejorar el ahorro de energía para el modo de baja energía.

### <a name="known-issues"></a>Problemas conocidos 
1. La función Date_Bucket de T-SQL no se puede usar en una columna calculada.


## <a name="ctp-23"></a>CTP 2.3
### <a name="sql-engine-build-number---15020001549"></a>Número de compilación del motor de SQL: 15.0.2000.1549
### <a name="whats-new"></a>Novedades
1. Compatibilidad con orígenes personalizados en la función Date_Bucket(). 
2. Compatibilidad con archivos BacPac como parte de la implementación de SQL.
3. Compatibilidad con la limpieza basada en directivas de retención de datos.      
   - Compatibilidad de DDL para habilitar la directiva de retención 
   - Limpieza procedimientos almacenados y tarea de limpieza en segundo plano
   - Eventos extendidos para supervisar tareas de limpieza

### <a name="fixes"></a>Correcciones
1. Mensajes de error adicionales y detalles para solucionar problemas de operaciones de streaming de TSQL. 
2. Mejoras para conservar la duración de la batería en modo inactivo. 
3. Correcciones del motor de streaming de TSQL: 
   - Corrección del problema de marca de agua atascada con la ventana de salto de subtransmisión 
   - Corrección del control de excepciones del marco para asegurarse de que se recopila como un error que se pueda procesar por el usuario


## <a name="ctp-22"></a>CTP 2.2
### <a name="sql-engine-build-number---15020001546"></a>Número de compilación del motor de SQL: 15.0.2000.1546
### <a name="whats-new"></a>Novedades
1. Compatibilidad con contenedores que no son raíz 
2. Compatibilidad con la recopilación de datos de uso y diagnóstico 
3. Actualizaciones de streaming de T-SQL
   - Compatibilidad con los caracteres Unicode para nombres de objetos de secuencia

### <a name="fixes"></a>Correcciones
1. Actualizaciones de streaming de T-SQL
   - Mejoras en la limpieza del proceso
   - Mejoras en el registro y los diagnósticos
2. Mejora del rendimiento de la ingesta de datos

## <a name="ctp-21"></a>CTP 2.1 
### <a name="sql-engine-build-number---15020001545"></a>Número de compilación del motor de SQL: 15.0.2000.1545
### <a name="fixes"></a>Correcciones
1. Corrección de PREDICT con modelos de ONNX para administrar el problema de CPUID en ARM 
2. Corrección para mejorar el control de la ruta de acceso de error en el inicio de la transmisión de TSQL 
3. Corrección del valor incorrecto del retraso de la marca de agua en las métricas de trabajo cuando no hay datos 
4. Corrección del problema con el adaptador de salida cuando el adaptador tiene un esquema de variables entre lotes  

## <a name="ctp-20"></a>CTP 2.0 
### <a name="sql-engine-build-number---15020001401"></a>Número de compilación del motor de SQL: 15.0.2000.1401
### <a name="whats-new"></a>Novedades
1.  Actualización del nombre de producto a "Azure SQL Edge"
1.  Función Date_bucket

    i.  Compatibilidad con el tipo Date, Time, DateTime
3.  PREDICT con ONNX
    
    i.  Parámetro RUNTIME necesario para ONNX 
    
4.  Compatibilidad con streaming de TSQL (versión preliminar limitada) 
 
### <a name="known-issues"></a>Problemas conocidos

1. <b>Problema:</b> posibles errores al aplicar dacpac en el inicio debido a un problema de temporización.

    <b>Solución alternativa:</b> con el reinicio de SQL Server o el contenedor se intentará de nuevo la aplicación de dacpac, con lo que el problema debería solucionarse.
### <a name="request-support"></a>Solicitud de soporte técnico
1. Puede solicitar soporte técnico en la [página de soporte técnico](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest).

4. Asegúrese de que están seleccionados los campos siguientes: 
    * Tipo de problema: Técnico 
    * Servicio: IoT Edge
    * Tipo de problema: Mi problema está relacionado con un módulo de IoT Edge
    * Subtipo de problema: Azure SQL Edge

   ![Incidencia de soporte técnico de ejemplo](media/get-support/support-ticket.png)

## <a name="ctp-15"></a>CTP 1.5
### <a name="sql-engine-build-number---15020001331"></a>Número de compilación del motor de SQL: 15.0.2000.1331
### <a name="whats-new"></a>Novedades
1. Función Date_bucket
    
    i. Compatibilidad con el tipo DateTimeOffset
2. Modelos de PREDICT con ONNX

    i. Compatibilidad con nvarchar
 
## <a name="ctp-14"></a>CTP 1.4
### <a name="sql-engine-build-number---15020001247"></a>Número de compilación del motor de SQL: 15.0.2000.1247
### <a name="whats-new"></a>Novedades
1.  Modelos de PREDICT con ONNX
 
    i.  Compatibilidad con Varchar
    
    ii. Migración a la versión en tiempo de ejecución de ONNX 1.0 
2.  Compatibilidad con características: Están habilitadas las siguientes características:

    i.   Compatibilidad con CDC

    ii.  Tabla de historial con compresión

    iii. Mayor factor de escala para la lectura anticipada del registro

    iv.  Modo por lotes frente a aplicación de filtro

    v.   Optimizaciones de lectura anticipada
 
## <a name="ctp-13"></a>(CTP 1.3)
### <a name="sql-engine-build-number---15020001147"></a>Número de compilación del motor de SQL: 15.0.2000.1147
### <a name="whats-new"></a>Novedades
1. Implementación del portal de Azure IoT 

    i.   Compatibilidad con la implementación de imágenes de AMD64 y ARM

    ii.  Compatibilidad con la creación de trabajos de streaming

    iii. Implementación de dacpac
2. Modelos de PREDICT con ONNX

    i. Compatibilidad con tipos numéricos
3. Compatibilidad con características: están habilitadas las siguientes características:

    i.  Agregado de aplicación a examen de almacén de columnas

    ii. Recorridos cícliclos
4. Trabajo de reducción del consumo de memoria y superficie
