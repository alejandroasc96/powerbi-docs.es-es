---
title: Solución de problemas de inicio de sesión en Power BI Desktop
description: Soluciones a problemas comunes para iniciar sesión en Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: ''
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 2e1653261663c5112662898c90f38df573f37c17
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-sign-in-for-power-bi-desktop"></a>Solución de problemas de inicio de sesión en Power BI Desktop
Puede haber ocasiones en que intente iniciar sesión en **Power BI Desktop** pero encuentre errores. Son dos los motivos principales que provocan errores en el inicio de sesión: **errores de autenticación en el proxy** y **errores de redireccionamiento a direcciones URL que no son HTTPS**. 

Para determinar qué está causando el problema de inicio de sesión, el primer paso es ponerse en contacto con el administrador y proporcionar información de diagnóstico para que pueda determinar la causa del problema. Mediante un seguimiento de los problemas asociados con su dificultad para iniciar sesión, los administradores pueden determinar cuál de los siguientes errores se aplica al usuario. 

Veamos cada uno de ellos por separado. Al final de este artículo encontrará información sobre cómo capturar un *seguimiento* en Power BI Desktop, lo cual puede ayudarle a realizar un seguimiento de los problemas.


## <a name="proxy-authentication-required-error"></a>Error de requerimiento de autenticación de proxy

En la pantalla siguiente se muestra un ejemplo del error *Se requiere autenticación del proxy*.

![Error de inicio de sesión para el error de autenticación de proxy](media/desktop-troubleshooting-sign-in/desktop-tshoot-sign-in_01.png)

Las siguientes excepciones en los archivos de seguimiento de *Power BI Desktop* están asociadas a este error:

* *Microsoft.PowerBI.Client.Windows.Services.PowerBIWebException*
* *HttpStatusCode: ProxyAuthenticationRequired*

Cuando se produce este error, el motivo más probable es que un servidor de autenticación de proxy de la red esté bloqueando las solicitudes web emitidas por **Power BI Desktop**. 

Si la red usa un servidor de autenticación de proxy, el administrador puede solucionar este problema creando listas blancas con los dominios siguientes en el servidor de autenticación de proxy:

* app.powerbi.com
* api.powerbi.com
* dominios en el espacio de nombres *.analysis.windows.net

En el caso de los clientes que forman parte de una nube gubernamental, este problema puede solucionarse creando listas blancas con los dominios siguientes en el servidor de autenticación del proxy:

* app.powerbigov.us
* api.powerbigov.us
* dominios en el espacio de nombres *.analysis.usgovcloudapi.net

## <a name="non-https-url-redirect-not-supported-error"></a>Error de que no se admite el redireccionamiento a direcciones URL que no son HTTPS

Las versiones actuales de **Power BI Desktop** usan la versión actual de la Biblioteca de autenticación de Active Directory (ADAL), que no permite un redireccionamiento a direcciones URL no seguras (no HTTPS). 

Las siguientes excepciones en los archivos de seguimiento de *Power BI Desktop* están asociadas a este error:

* *Microsoft.IdentityModel.Clients.ActiveDirectory.AdalServiceException: Non-HTTPS url redirect is not supported in webview*
* *ErrorCode: non_https_redirect_failed*

Si se produce el error *ErrorCode: non_https_redirect_failed*, una o varias páginas o proveedores de redireccionamiento de la cadena de redireccionamiento no son un punto de conexión protegido con HTTPS, o un emisor de certificados de uno o varios redireccionamientos no está entre las raíces de confianza del dispositivo. Todos los proveedores de cualquier cadena de redireccionamiento de inicio de sesión deben usar una dirección URL HTTPS. Para solucionar este problema, póngase en contacto con el administrador y solicite que se usen direcciones URL seguras para sus sitios de autenticación. 

## <a name="how-to-collect-a-trace-in-power-bi-desktop"></a>Recopilación de un seguimiento en Power BI Desktop

Para recopilar un seguimiento en **Power BI Desktop**, siga estos pasos:

1. Habilite el seguimiento en **Power BI Desktop**; para ello, vaya a **Archivo > Opciones y configuración > Opciones** y seleccione **Diagnósticos** en las opciones en el panel izquierdo. En el panel que aparece, active la casilla junto a **Habilitar seguimiento**, tal y como se muestra en la siguiente imagen. Es posible que tenga que reiniciar **Power BI Desktop**.
   
   ![Habilitación del seguimiento en Power BI Desktop](media/desktop-troubleshooting-sign-in/desktop-tshoot-sign-in_02.png)

2. A continuación, siga estos pasos que reproducen el error. Cuando esto sucede, **Power BI Desktop** agrega eventos en el registro de seguimiento, que se guarda en el equipo local.

3. Navegue hasta la carpeta de seguimientos en el equipo local. Puede encontrar esa carpeta seleccionando el vínculo de **Diagnósticos** donde habilitó el seguimiento, que se muestra como *Permite abrir la carpeta de volcado de memoria y seguimiento* en la imagen anterior. A menudo esto se encuentra en el equipo local en la siguiente ubicación:

    `C:\Users/<user name>/AppData/Local/Microsoft/Power BI Desktop/Traces`

Puede haber muchos archivos de seguimiento en esa carpeta. Asegúrese de que sólo envía los archivos recientes al administrador para facilitarle una rápida identificación del error. 
