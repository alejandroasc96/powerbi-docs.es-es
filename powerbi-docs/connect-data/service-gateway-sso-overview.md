---
title: Introducción al inicio de sesión único (SSO) para puertas de enlace de Power BI
description: Configure la puerta de enlace para habilitar el inicio de sesión único (SSO) desde Power BI a orígenes de datos locales.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 4a4bb6ccb74ce08ea1ff63f44b1c2c5406c527ad
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85231311"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>Introducción al inicio de sesión único (SSO) para puertas de enlace de Power BI

Puede lograr una conectividad de inicio de sesión único perfecta si habilita la actualización en tiempo real de los informes y paneles de Power BI a partir de los datos locales, mediante la configuración de la puerta de enlace de datos local. Puede configurar la puerta de enlace con delegación restringida de [Kerberos](service-gateway-sso-kerberos.md) o con Lenguaje de marcado de aserción de seguridad ([SAML](service-gateway-sso-saml.md)). La puerta de enlace de datos local admite el inicio de sesión único mediante [DirectQuery](desktop-directquery-about.md) o para actualizar, lo que conecta a los orígenes de datos locales. 

Power BI admite los siguientes orígenes de datos:

* SQL Server (Kerberos)
* SAP HANA (Kerberos y SAML)
* Servidor de aplicaciones de SAP BW (Kerberos)
* Servidor de mensajes de SAP BW (Kerberos) 
* Oracle (Kerberos) 
* Teradata (Kerberos)
* Spark (Kerberos)
* Impala (Kerberos)

En la actualidad no se admite el inicio de sesión único para [extensiones de M](https://github.com/microsoft/DataConnectors/blob/master/docs/m-extensions.md).

Cuando un usuario interactúa con un informe de DirectQuery en el servicio Power BI, cada operación de filtro cruzado, división, ordenación y edición de informes puede dar lugar a consultas que se ejecutan en vivo en el origen de datos local subyacente. Cuando se configura el inicio de sesión único para el origen de datos, las consultas se ejecutan bajo la identidad del usuario que interactúa con Power BI (es decir, a través de la experiencia web o las aplicaciones móviles de Power BI). Por lo tanto, cada usuario ve exactamente los datos para los que tiene permiso en el origen de datos subyacente. 

También puede configurar un informe definido para actualización en el servicio Power BI para que use SSO. Al configurar SSO para este origen de datos, las consultas se ejecutan bajo la identidad del propietario del conjunto de datos en Power BI, de modo que la actualización se produce en función de los permisos del propietario del conjunto de datos en el origen de datos subyacente. Actualmente, la actualización mediante SSO está habilitada solo en los orígenes de datos que usan la delegación restringida de [Kerberos](service-gateway-sso-kerberos.md). 

## <a name="query-steps-when-running-sso"></a>Pasos de consulta cuando se ejecuta SSO

Una consulta que se ejecuta con SSO consta de tres pasos, tal como se muestra en el diagrama siguiente.

![Pasos de consulta de SSO](media/service-gateway-sso-overview/sso-query-steps.png)

Estos son los detalles adicionales sobre cada paso:

1. Para cada consulta, el servicio Power BI incluye el *nombre principal de usuario (UPN)* —es decir, el nombre de usuario completo del usuario que con sesión iniciada actualmente en el servicio Power BI— al enviar una solicitud de consulta a la puerta de enlace configurada.

2. La puerta de enlace debe asignar el UPN de Azure Active Directory a una identidad de Active Directory local:

   a. Si Azure AD DirSync (también conocido como *Azure AD Connect*) está configurado, la asignación funciona automáticamente en la puerta de enlace.

   b.  En caso contrario, la puerta de enlace puede buscar y asignar el UPN de Azure AD a un usuario de AD local mediante la realización de una búsqueda en el dominio local de Active Directory.

3. El proceso del servicio de puerta de enlace suplanta al usuario local asignado, abre la conexión a la base de datos subyacente y después envía la consulta. No es necesario instalar la puerta de enlace en la misma máquina que la base de datos.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ya entiende los conceptos básicos de la activación del inicio de sesión único a través de la puerta de enlace, lea información más detallada sobre Kerberos y SAML:

* [Inicio de sesión único (SSO): Kerberos](service-gateway-sso-kerberos.md)
* [Inicio de sesión único (SSO): SAML](service-gateway-sso-saml.md)
