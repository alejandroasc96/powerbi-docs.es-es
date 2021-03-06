---
title: Solución de problemas del desarrollo de objetos visuales de Power BI
description: En este artículo se examinan algunos problemas comunes que pueden encontrarse al desarrollar o crear un objeto visual personalizado de Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: troubleshooting
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
ms.openlocfilehash: bfdca7f5652106271ba46f0cffd2759b7b4595eb
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "85485631"
---
# <a name="troubleshoot-power-bi-visuals"></a>Solución de problemas con los objetos visuales de Power BI

## <a name="debug"></a>Depurar

**No se ha encontrado el comando de pbiviz (o errores similares)**

Si ejecuta `pbiviz` en la línea de comandos del terminal, verá la pantalla de ayuda. De lo contrario, no está instalado correctamente. Asegúrese de que tiene instalada al menos la versión 4.0 de NodeJS.

**No se puede encontrar el objeto visual de depuración en la pestaña Visualizaciones**

El objeto visual de depuración es similar a un icono de símbolo del sistema en la pestaña **Visualizaciones**.

![Selección del objeto visual](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Si no lo ve, asegúrese de que lo ha habilitado en la configuración de Power BI.

> [!NOTE]
> Actualmente, el objeto visual de depuración solo está disponible en el servicio Power BI y no está en Power BI Desktop ni en la aplicación móvil. El objeto visual empaquetado seguirá funcionando en todas partes.

**No puede ponerse en contacto con el servidor del objeto visual**

Ejecute el servidor del objeto visual con el comando `pbiviz start` en línea de comandos del terminal desde la raíz del proyecto del objeto visual. Si el servidor no se está ejecutando, es probable que los certificados SSL no se hayan instalado correctamente.

Si tiene alguna pregunta o problema, o quiere hacer un comentario, no dude en ponerse en contacto con el equipo de soporte técnico de los objetos visuales de Power BI (pbicvsupport@microsoft.com).

## <a name="next-steps"></a>Pasos siguientes

Para más información, visite [Preguntas más frecuentes sobre objetos visuales de Power BI](power-bi-custom-visuals-faq.md#organizational-power-bi-visuals).