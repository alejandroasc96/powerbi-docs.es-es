---
title: Adición de comentarios en paneles e informes
description: En este documento se explica cómo agregar comentarios en un panel, un informe o un objeto visual, y cómo usar los comentarios para mantener conversaciones con los colaboradores.
author: mihart
ms.reviewer: mihart
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 07/07/2020
ms.author: mihart
LocalizationGroup: Consumer
ms.openlocfilehash: 76a3bd087899126d1c3aa9eed6eb7d20b1441bff
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86161902"
---
# <a name="add-comments-to-a-dashboard-or-report"></a>Adición de comentarios en un panel o informe

[!INCLUDE[consumer-appliesto-ynny](../includes/consumer-appliesto-ynny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Agregue un comentario personal o empiece una conversación sobre un panel o informe con sus compañeros. La característica **Comentarios** es solo una de las formas que tiene un *consumidor* de colaborar con otros. 

![vídeo sobre los comentarios](media/end-user-comment/comment.gif)

> [!NOTE]
> La colaboración con otros usuarios, incluido agregar comentarios a los informes compartidos, requiere una licencia de Power BI Pro o Premium. [¿Qué licencia tengo?](end-user-license.md)

## <a name="how-to-use-the-comments-feature"></a>Cómo usar la característica Comentarios
Se pueden agregar comentarios a un panel completo, a objetos visuales individuales en un panel, a una página de informe, a un informe paginado y a objetos visuales individuales en una página de informe. Agregue un comentario general o un comentario dirigido a compañeros específicos.  

Al agregar un comentario en un informe, Power BI captura los valores actuales de filtro y segmentación, y crea un [marcador](end-user-bookmarks.md). Esto significa que, al seleccionar un comentario o responder a él, la página o el objeto visual del informe pueden cambiar para mostrar la selección de filtros y la segmentación de datos que estaban activas al agregar el comentario inicialmente.  

![Vídeo que muestra un informe con filtros](media/end-user-comment/power-bi-comment.gif)

¿Por qué esto es importante? Supongamos que un compañero ha aplicado un filtro que revela información interesante que quiere compartir con el equipo. Sin ese filtro seleccionado, es posible que el comentario no tenga sentido.

Si está usando un informe paginado, solo puede dejar un comentario general sobre el informe.  No se permite dejar comentarios en objetos visuales de informes paginados individuales.

### <a name="add-a-general-comment-to-a-dashboard-or-report"></a>Adición de un comentario general en un panel o informe
El proceso para agregar comentarios en un panel o informe es similar.  En este ejemplo, usaremos un panel. 

1. Abra un panel de Power BI y seleccione el icono **Comentarios**. Se abre el cuadro de diálogo Comentarios.

    ![icono de comentarios](media/end-user-comment/power-bi-comments-icon.png)

    Aquí vemos que el creador del panel ya agregó un comentario general.  Cualquier persona con acceso a este panel puede ver este comentario.

    ![icono de comentarios](media/end-user-comment/power-bi-first-comment.png)

2. Para responder, seleccione **Responder**, escriba la respuesta y seleccione **Publicar**.  

    ![Icono de respuesta a comentarios](media/end-user-comment/power-bi-comments-reply.png)

    De manera predeterminada, Power BI dirige la respuesta al compañero que inició el hilo de comentarios, en este caso, Aaron. 

    ![Comentario con respuesta](media/end-user-comment/power-bi-respond.png)

 3. Si quiere agregar un comentario que no forme parte de ningún hilo de comentarios, escriba el comentario en el campo de texto superior.

    ![Icono de respuesta a comentarios](media/end-user-comment/power-bi-new-commenting.png)

    Los comentarios sobre este panel ahora tendrán este aspecto.

    ![Conversaciones de comentarios](media/end-user-comment/power-bi-conversation.png)

### <a name="add-a-comment-to-a-specific-dashboard-or-report-visual"></a>Adición de un comentario en objeto visual de un panel o informe concreto
Además de agregar comentarios en un panel completo o en toda una página de un informe, puede agregar comentarios en iconos u objetos visuales concretos del panel o informe en cuestión. Los procesos son similares; en este ejemplo usaremos un informe.

1. Mantenga el puntero sobre el objeto visual y seleccione **Más opciones** (...).    
2. En la lista desplegable, seleccione **Abrir comentarios**.

    ![Agregar un comentario es la primera elección](media/end-user-comment/power-bi-comment-reports.png)  

3.  Se abre el cuadro de diálogo **Comentarios**, y los demás objetos visuales de la página aparecen atenuados. El objeto visual aún no tiene comentarios. 

    ![Agregar un comentario para mí](media/end-user-comment/power-bi-comments-column.png)  

4. Escriba un comentario y seleccione **Publicar**.

    ![Agregar un comentario para mí](media/end-user-comment/power-bi-comment-logistics.png)  

    - Al seleccionar un comentario escrito en un objeto visual, en la página del informe, dicho objeto visual queda resaltado (ver arriba).

    - En un panel, el icono de gráfico ![comentario con icono de gráfico](media/end-user-comment/power-bi-comment-chart-icon.png) nos permite saber que un comentario está asociado a un objeto visual específico. Los comentarios que se aplican a todo el panel no tienen ningún icono especial. Al seleccionar el icono de gráfico, el objeto visual relacionado queda resaltado en el panel.
    

    ![objeto visual relacionado resaltado](media/end-user-comment/power-bi-highlight.png)

5. Seleccione **Cerrar** para volver al panel o al informe.

### <a name="get-your-colleagues-attention-by-using-the--sign"></a>Llamar la atención de sus compañeros mediante el signo @
Ya sea que cree un comentario de panel, de informe, de icono o de objeto visual, puede captar la atención de sus compañeros mediante el símbolo "\@".  Cuando se escribe el símbolo "\@", Power BI abre una lista desplegable donde puede buscar y seleccionar personas de la organización. Cualquier nombre comprobado precedido por el símbolo "\@" se muestra en una fuente de color azul. Los usuarios @mentioned recibirán inmediatamente un mensaje de correo electrónico en su Bandeja de entrada y, si usan una aplicación de Power BI Mobile, una notificación de inserción en su dispositivo. Pueden abrir el comentario directamente desde la notificación, ver los datos y responder según corresponda.

Esta es una conversación que estoy manteniendo con el *diseñador* de la visualización. Usa el símbolo @ para asegurarse de que vea el comentario. Recibo una notificación y selecciono el vínculo para abrir este panel y la conversación correspondiente.  

![Agregar una mención en el comentario](media/end-user-comment/power-bi-comment-convo.png)  

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas

- Los marcadores no se capturan cuando se responde a una conversación. Solo el primer comentario de una conversación crea un marcador.

## <a name="next-steps"></a>Pasos siguientes
Volver a [Visualizaciones para consumidores](end-user-visualizations.md)    
<!--[Select a visualization to open a report](end-user-open-report.md)-->
