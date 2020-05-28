---
title: Direcciones URL de Power BI para la inclusión en listas blancas
description: En este artículo se enumeran los puntos de conexión de dirección URL y los puertos de la lista segura para la conectividad a Power BI.
author: kfollis
ms.author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.custom: seodec18
ms.openlocfilehash: f74bfb92508564a01422729eefc251acc124baea
ms.sourcegitcommit: 250242fd6346b60b0eda7a314944363c0bacaca8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692732"
---
# <a name="power-bi-urls-for-whitelisting"></a>Direcciones URL de Power BI para la inclusión en listas blancas
[//]: # "suparnap y miwehnia son contactos para mantener esta lista"

**El servicio Power BI en línea**, también conocido como la aplicación de SaaS (software como servicio) de Power BI, requiere conectividad a internet. Los clientes que usen el servicio Power BI en línea deben poder acceder a los puntos de conexión siguientes.

Para usar el servicio Power BI en línea, debe poder conectarse a los puntos de conexión marcados como **obligatorios** en las tablas siguientes y los puntos de conexión marcados como **obligatorios** en los sitios vinculados. Si el vínculo a un sitio externo hace referencia a una sección concreta, solo tiene que revisar los puntos de conexión de esa sección.

Los puntos de conexión marcados como **Opcional** también se pueden incluir en la **lista de permitidos** para que funcionen funcionalidades específicas.

El servicio Power BI en línea solo requiere que el puerto TCP 443 esté abierto para los puntos de conexión enumerados.

Los caracteres comodín (*) representan todos los niveles bajo el dominio raíz y usamos N/D cuando la información no está disponible. En la columna **Destinos**, se incluye una lista con FQDN, dominios y vínculos a sitios externos, que contienen más información sobre el punto de conexión.

>[!Important]
>La información de las tablas siguientes no representa la **nube del gobierno estadounidense**, **la nube de Alemania** ni **la nube de China**.

## <a name="authentication"></a>Autenticación

Power BI depende de los puntos de conexión requeridos en las secciones de identidad y autenticación de Microsoft 365. Para usar Power BI, debe poder conectarse a los puntos de conexión en el sitio vinculado a continuación.

| Fila | Propósito | Destinos | Puertos |
| --- | --- | --- | --- |
| 1 | **Obligatorio:** autenticación e identidad | Consulte la documentación para obtener las [direcciones URL de Microsoft 365 Common y Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online).  | N/D |

## <a name="general-site-usage"></a>Uso del sitio general

Para usar Power BI de forma general, debe poder conectarse a los puntos de conexión de la tabla y los sitios vinculados a continuación.

| Fila | Propósito | Destinos | Puertos |
| --- | --- | --- | --- |
| 1 | **Obligatorio:** API de back-end | *.analysis.windows.net | TCP 443 |
| 2 | **Obligatorio:** API de back-end | *.pbidedicated.windows.net | TCP 443 |
| 3 | **Obligatorio:** Content Delivery Network (CDN) | content.powerapps.com | TCP 443 |
| 4 | **Obligatorio:** Integración de Microsoft 365 | Consulte la documentación para obtener las [direcciones URL de Microsoft 365 Common y Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online). | N/D |
| 5 | **Obligatorio:** Portal | app.powerbi.com | TCP 443 |
| 6 | **Obligatorio:** telemetría de servicio | dc.services.visualstudio.com | TCP 443 |
| 7 | **Opcional:** mensajes informativos | dynmsg.modpim.com | TCP 443 |
| 8 | **Opcional:** encuestas de NPS | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>Administración

Para realizar funciones administrativas en Power BI, debe poder conectarse a los puntos de conexión de los sitios vinculados a continuación.

| Fila | Propósito | Destinos | Puertos |
| --- | --- | --- | --- |
| 1 | **Obligatorio:** para administrar usuarios y ver los registros de auditoría | Consulte la documentación para obtener las [direcciones URL de Microsoft 365 Common y Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online). | N/D |
| | | |

## <a name="getting-data"></a>Obtención de datos

Para obtener datos de orígenes de datos específicos, como OneDrive, debe poder conectarse a los puntos de conexión de la tabla siguiente. Puede ser necesario tener acceso a dominios de internet y direcciones URL adicionales para orígenes de datos específicos usados en su organización.

| Fila | Propósito | Destinos | Puertos |
| --- | --- | --- | --- |
| 1 | **Obligatorio:** AppSource (aplicaciones internas o externas en Power BI) | appsource.microsoft.com <br> *.s-microsoft.com  | TCP 443 |
| 2 | **Opcional:** iniciar sesión y obtener datos para los paquetes de contenido | En función de los paquetes de contenido utilizados | En función de los paquetes de contenido utilizados |
| 3 | **Opcional:** importar archivos desde OneDrive Personal | Vea el sitio [Required URLs and ports for OneDrive](https://docs.microsoft.com/onedrive/required-urls-and-ports) (Direcciones y puertos requeridos para OneDrive) | N/D |
| 4 | **Opcional:** vídeo tutorial de Power BI en 60 segundos | *.doubleclick.net <br> *.ggpht.com <br> *.google.com <br> *.googlevideo.com <br> *.youtube.com <br> *.ytimg.com <br> fonts.gstatic.com | TCP 443 |
| 5 | **Opcional:** orígenes de datos de streaming de PubNub | Vea la [documentación de PubNub](https://support.pubnub.com/support/solutions/articles/14000043522) | N/D |
| | | |

## <a name="dashboard-and-report-integration"></a>Integración de paneles e informes

Power BI depende de determinados puntos de conexión para poder admitir los paneles e informes. Debe poder conectarse a los puntos de conexión de la tabla y los sitios vinculados a continuación.

| Fila | Propósito | Destinos | Puertos |
| --- | --- | --- | --- |
| 1 | **Obligatorio:** integración de Excel | Consulte la documentación para obtener las [direcciones URL de Microsoft 365 Common y Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online). | N/D |
| | | |

## <a name="power-bi-visuals"></a>Objetos visuales de Power BI

Power BI depende de determinados puntos de conexión para ver los objetos visuales de Power BI y acceder a ellos. Debe poder conectarse a los puntos de conexión de la tabla y los sitios vinculados a continuación.

| Fila | Propósito | Destinos | Puertos |
| --- | --- | --- | --- |
| 1 | **Obligatorio:** importar un objeto visual personalizado desde la interfaz de Marketplace o desde un archivo | *.azureedge.net <br> *.blob.core.windows.net <br> *.osi.office.net <br> *.msecnd.net <br> store.office.com <br> web.vortex.data.microsoft.com <br> store-images.s-microsoft.com | TCP 443 |
| 2 | **Opcional:** Mapas de Bing | bing.com <br> platform.bing.com <br> *.virtualearth.net | TCP 443 |
| 3 | **Opcional:** PowerApps | Vea la sección [Servicios requeridos](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) del sitio de requisitos del sistema de PowerApps | N/D |
| 4 | **Opcional:** Visio | Consulte la documentación para obtener las [direcciones URL de Microsoft 365 Common y Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online), además de [SharePoint Online y OneDrive para la Empresa](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business). | N/D |
| | | |

## <a name="related-external-sites"></a>Sitios externos relacionados

Vínculos de Power BI a otros sitios relacionados. Estos sitios hospedan documentación, soporte técnico, solicitudes de nuevas funciones, etc. El acceso a estos sitios no afectará a la funcionalidad de Power BI, por lo que la inclusión en listas blancas es opcional.

| Fila | Propósito | Destinos | Puertos |
| --- | --- | --- | --- |
| 1 | **Opcional:** sitio de la Comunidad | community.powerbi.com <br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **Opcional:** Sitio de documentación | docs.microsoft.com <br> img-prod-cms-rt-microsoft-com.akamaized.net <br> statics-uhf-eas.akamaized.net <br> cdnssl.clicktale.net <br> ing-district.clicktale.net | TCP 443 |
| 3 | **Opcional:** sitio de descarga (para Power BI Desktop, etc.) | download.microsoft.com | TCP 443 |
| 4 | **Opcional:** redirecciones externas | aka.ms <br> go.microsoft.com | TCP 443 |
| 5 | **Opcional:** sitio de comentarios de ideas| ideas.powerbi.com <br> powerbi.uservoice.com | TCP 443 |
| 6 | **Opcional:** sitio de Power BI: página de inicio, vínculos de más información, sitio de soporte técnico, vínculos de descarga, presentación de asociados, etc. | powerbi.microsoft.com | TCP 443 |
| 7 | **Opcional:** Centro para desarrolladores de Power BI | dev.powerbi.com | TCP 443 |
| 8 | **Opcional:** sitio de soporte técnico | support.powerbi.com <br> s3.amazonaws.com <br> *. olark.com <br> logx.optimizely.com <br> mscom.demdex.net <br> tags.tiqcdn.com | TCP 443 |
| | | |
