---
title: 'Servicio de terceros: Conector de Google Analytics'
description: 'Servicio de terceros: Conector de Google Analytics para Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 3247e718e5e98536ddce3a253f8e78e5ff615614
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85234461"
---
# <a name="use-the-google-analytics-connector-for-power-bi-desktop"></a>Uso del conector de Google Analytics para Power BI Desktop
> [!NOTE]
> El paquete de contenido de Google Analytics y el conector de Power BI Desktop se basan en la API de informes centrales de Google Analytics. Por lo tanto, las características y la disponibilidad pueden variar con el tiempo.

Puede conectarse a los datos de Google Analytics mediante el conector de **Google Analytics**. Para conectarse, siga estos pasos:

1. En **Power BI Desktop**, seleccione **Obtener datos** en la cinta de opciones **Inicio**.
2. En la ventana **Obtener datos**, seleccione **Servicios en línea** en las categorías del panel izquierdo.
3. Seleccione **Google Analytics** en las selecciones del panel derecho.
4. En la parte inferior de la ventana, seleccione **Conectar**.  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Se muestra un cuadro de diálogo que explica que el conector es un servicio de terceros y le advierte acerca de cómo las características y la disponibilidad pueden cambiar con el tiempo, entre otras aclaraciones.  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

Al seleccionar **Continuar**, se le pedirá que inicie sesión en Google Analytics.  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

Cuando escriba sus credenciales, se indicará que a Power BI le gustaría tener acceso sin conexión. Así es como se usa **Power BI Desktop** para acceder a los datos de Google Analytics.  

Tras la aceptación, **Power BI Desktop** muestra que tiene la sesión iniciada.  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

Seleccione **Conectar**. Los datos de Google Analytics se conectan a **Power BI Desktop** y se cargan los datos.  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>Cambios en la API
Aunque intentamos sacar actualizaciones para cualquier cambio, la API puede cambiar de manera que afectE a los resultados de las consultas que generamos. En algunos casos, puede que ya no se admitan determinadas consultas. Debido a esta dependencia, no podemos garantizar los resultados de las consultas cuando se usa este conector.

Para más detalles sobre los cambios en la API de Google Analytics, consulte el [registro de cambios](https://developers.google.com/analytics/devguides/changelog).

