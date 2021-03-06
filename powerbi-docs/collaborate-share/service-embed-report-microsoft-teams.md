---
title: Colaboración en Microsoft Teams con Power BI
description: Con la pestaña Power BI de Microsoft Teams, puede insertar fácilmente informes interactivos en canales y chats.
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
LocalizationGroup: Share your work
ms.date: 06/05/2020
ms.openlocfilehash: aedc65b1d13c25068d4bc19026e1475081336e77
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85226389"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Colaboración en Microsoft Teams con Power BI

Con la pestaña **Power BI** actualizada de Microsoft Teams, puede insertar fácilmente informes interactivos en canales y chats de Microsoft Teams. Use la pestaña **Power BI** de Microsoft Teams para que sus compañeros encuentren fácilmente los datos que el equipo usa, así como para analizar los datos de los canales del equipo. Cuando pegue un vínculo a los informes, a los paneles y a las aplicaciones en el cuadro de mensaje de Microsoft Teams, la vista previa del vínculo mostrará información sobre este. Use el botón **Compartir en Teams** para iniciar conversaciones rápidamente al ver informes y paneles en Power BI.

## <a name="requirements"></a>Requisitos

Para que la pestaña **Power BI** de Microsoft Teams funcione, asegúrese de lo siguiente:

- Los usuarios tienen una licencia de Power BI Pro o el informe está incluido en una [capacidad de Power BI Premium (SKU EM o P)](../admin/service-premium-what-is.md) con una licencia de Power BI.
- Microsoft Teams tiene la pestaña **Power BI**.
- Los usuarios han iniciado sesión en el servicio Power BI para activar la licencia de Power BI y consumir el informe.
- Para agregar un informe en Microsoft Teams con la pestaña **Power BI**, debe tener como mínimo un rol de visor en el área de trabajo que hospeda el informe. Consulte [Roles en las nuevas áreas de trabajo](service-new-workspaces.md#roles-in-the-new-workspaces) para obtener información sobre los distintos roles.
- Para ver el informe en la pestaña **Power BI** de Microsoft Teams, los usuarios deben tener permiso para ver el informe.
- Los usuarios deben ser usuarios de Microsoft Teams con acceso a canales y chats.

Para que las vistas previas de vínculos funcionen, asegúrese de lo siguiente:

- Los usuarios cumplen los requisitos para usar la pestaña **Power BI** de Microsoft Teams.
- Los usuarios han iniciado sesión en Power BI.

Para que funcionen los botones de **Compartir en Teams**, asegúrese de lo siguiente:

- Los usuarios cumplen los requisitos para usar la pestaña **Power BI** de Microsoft Teams.
- Los usuarios han iniciado sesión en Power BI.
- Los administradores de Power BI no han deshabilitado la configuración del inquilino **Compartir en Teams**.


## <a name="embed-your-report"></a>Insertar un informe

Siga estos pasos para insertar el informe en un canal o un chat de Microsoft Teams.

1. Abra un canal o un chat en Microsoft Teams y seleccione el icono **+** .

    ![Adición de una pestaña a un canal o un chat](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

1. Seleccione la pestaña **Power BI**.

    ![Lista de pestañas de Microsoft Teams con la pestaña Power BI](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

1. Use las opciones proporcionadas para elegir un informe de un área de trabajo o una aplicación de Power BI.

    ![Configuración de la pestaña Power BI de Microsoft Teams](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

1. El nombre de la pestaña se actualiza automáticamente para que coincida con el nombre del informe, pero puede cambiarlo.

1. Seleccione **Guardar**.

## <a name="supported-reports-for-embedding-the-power-bi-tab"></a>Informes admitidos para su inserción en la pestaña Power BI

Puede insertar los siguientes tipos de informes en la pestaña **Power BI**:

- Informes paginados e interactivos.
- Informes de **Mi área de trabajo**, de una nueva experiencia de área de trabajo y de áreas de trabajo clásicas.
- Informes de aplicaciones de Power BI.

## <a name="get-a-link-preview"></a>Obtención de una vista previa de vínculo

Siga estos pasos para obtener una vista previa de vínculo para el contenido en el servicio Power BI.

1. Copie un vínculo a un informe, un panel o una aplicación en el servicio Power BI. Por ejemplo, copie el vínculo de la barra de direcciones del explorador.

1. Pegue el vínculo en el cuadro de mensaje de Microsoft Teams. Si se le pide, inicie sesión en el servicio de vista previa de vínculo. Es posible que tenga que esperar unos segundos para que se cargue la vista previa del vínculo.

    ![Inicio de sesión en el bot de Power BI](media/service-embed-report-microsoft-teams/service-teams-link-preview-sign-in-needed.png)

1. Una vez que se ha iniciado sesión correctamente, se muestra la vista previa de vínculo básica.

    ![Vista previa de vínculo básica](media/service-embed-report-microsoft-teams/service-teams-link-preview-basic.png)

1. Seleccione el icono **Expandir** para mostrar la tarjeta de vista previa enriquecida.

    ![icono de Expandir](media/service-embed-report-microsoft-teams/service-teams-link-preview-expand-icon.png)

1. La tarjeta de vista previa de vínculo enriquecida incluye el vínculo y los botones de acción pertinentes.

    ![Tarjeta de vista previa de vínculo enriquecida](media/service-embed-report-microsoft-teams/service-teams-link-preview-nice-card.png)

1. Envíe el mensaje.

## <a name="share-to-teams-buttons-in-the-power-bi-service"></a>Botones de Compartir en Teams en el servicio Power BI

Siga estos pasos para compartir vínculos a canales y chats de Microsoft Teams al ver informes o paneles en el servicio Power BI.

1. Use los botones de **Compartir en Teams** de la barra de acciones o el menú contextual de un objeto visual específico.

   * Botón **Compartir en Teams** de la barra de acciones:

       ![Botón Compartir en Teams de la barra de acciones](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-action-bar-button.png)
    
   * Botón **Compartir en Teams** del menú contextual del objeto visual:
    
      ![Botón Compartir en Teams en el menú contextual de un objeto visual](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-visual-context-menu.png)

1. En el cuadro de diálogo **Compartir en Microsoft Teams**, seleccione el canal o las personas a las que desea enviar el vínculo. Si lo desea, puede escribir un mensaje. Es posible que se le pida que inicie sesión primero en Microsoft Teams.

    ![Cuadro de diálogo Compartir en Microsoft Teams con información y mensaje](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-dialog.png)

1. Seleccione **Compartir** para enviar el vínculo.
    
1. El vínculo se agrega a las conversaciones existentes o inicia un nuevo chat.

    ![Conversación de Microsoft Teams con vínculo a un elemento de Power BI](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-deep-link.png)

1. Seleccione el vínculo para abrir el elemento en el servicio Power BI.

1. Si usa el menú contextual para un determinado objeto visual, este se resaltará cuando se abra el informe.

    ![Informe de Power BI abierto con un objeto visual específico resaltado](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-spotlight-visual.png)
    

## <a name="grant-access-to-reports"></a>Concesión de acceso a los informes

El hecho de insertar un informe en Microsoft Teams o enviar un vínculo a un elemento no concede permiso a los usuarios para ver el informe de forma automática. Debe [permitir que los usuarios vean los informes en Power BI](service-share-dashboards.md). Para que esto sea más fácil, puede usar un grupo de Microsoft 365 para el equipo.

> [!IMPORTANT]
> Asegúrese de revisar quién puede ver el informe en el servicio Power BI y de conceder acceso a los usuarios que no están en la lista.

Una forma de garantizar que todos los miembros del equipo tengan acceso a los informes consiste en incluir los informes en una misma área de trabajo y dar acceso a ese grupo de Microsoft 365 del equipo al área de trabajo en cuestión.

## <a name="link-previews"></a>Vistas previas de vínculo

Se proporcionan vistas previas de vínculo para los siguientes elementos de Power BI:
- Informes
- Paneles
- Aplicaciones

El servicio de vista previa de vínculo requiere que los usuarios inicien sesión. Para cerrar la sesión, seleccione el icono de **Power BI** en la parte inferior del cuadro de mensaje. Después, seleccione **Cerrar sesión**.

## <a name="start-a-conversation"></a>Iniciar una conversación

Cuando se agrega una pestaña de informe de Power BI a Microsoft Teams, este crea de forma automática una pestaña de conversación para el informe.

- Seleccione el icono**Mostrar la ficha Conversación** en la esquina superior derecha.

    ![Icono Mostrar la ficha Conversación](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-icon.png)

    El primer comentario es un vínculo al informe. Todos los usuarios de ese canal de Microsoft Teams pueden ver y analizar el informe en la conversación.

    ![Ficha Conversación](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-tab.png)
    
## <a name="share-to-teams-tenant-setting"></a>Configuración de inquilino Compartir en Teams

La configuración del inquilino **Compartir en Teams** en el portal de administración de Power BI permite que las organizaciones oculten los botones de **Compartir en Teams**. Cuando se deshabilita, los usuarios no verán los botones de **Compartir en Teams** en la barra de acciones ni en los menús contextuales cuando ven informes y paneles en el servicio Power BI.

![Configuración de inquilino Compartir en Teams en el portal de administración de Power BI](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-tenant-setting.png)

## <a name="known-issues-and-limitations"></a>Limitaciones y problemas conocidos

- Power BI no admite los mismos idiomas localizados que Microsoft Teams. En consecuencia, es posible que no vea una localización correcta en el informe insertado.
- En la pestaña **Power BI** de Microsoft Teams no se pueden insertar paneles de Power BI.
- Los usuarios que no tengan una licencia o permiso de Power BI para acceder al informe verán el mensaje "El contenido no está disponible".
- Es posible que tenga problemas si usa Internet Explorer 10. <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- La pestaña **Power BI** de Microsoft Teams no admite [filtros de URL](service-url-filters.md).
- En nubes nacionales, la nueva pestaña **Power BI** no está disponible. Puede que haya disponible una versión anterior que no es compatible con la nueva experiencia de área de trabajo o los informes de aplicaciones de Power BI.
- Una vez que se guarde la pestaña, no se podrá cambiar su nombre en la configuración. Para cambiarlo, use la opción **Cambiar nombre**.
- No se admite el inicio de sesión único para el servicio de vista previa de vínculo.
- Las vistas previas de vínculo no funcionan en los canales privados o de chat.
- Es posible que los botones de **Compartir en Teams** no funcionen si el explorador usa una configuración de privacidad estricta. Use la opción **¿Ha encontrado algún problema? Intente abrir en una nueva ventana** si el cuadro de diálogo no se abre correctamente.
- **Compartir en Teams** no incluye una vista previa de vínculo.
- Las vistas previas de vínculos y **Compartir en Teams** no conceden permisos a los usuarios para ver el elemento. Los permisos deben administrarse por separado.
- El botón**Compartir en Teams** no está disponible en los menús contextuales de objetos visuales cuando el autor de un informe establece la opción **Más** en *Desactivado* para el objeto visual.

## <a name="next-steps"></a>Pasos siguientes

- [Compartir un panel con compañeros y otros usuarios](service-share-dashboards.md)
- [Creación y distribución de una aplicación en Power BI](service-create-distribute-apps.md)
- [¿Qué es Power BI Premium?](../admin/service-premium-what-is.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/).
