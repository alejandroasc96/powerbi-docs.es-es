---
title: Administración del formulario de inicio de sesión de Power BI Desktop por parte de los administradores
description: Aprenda a administrar el formulario de inicio de sesión inicial al abrir Power BI Desktop.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 49b7d1129f73e146db1e34b1ec7d39a176cb37ed
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85228911"
---
# <a name="administrators-manage-the-power-bi-desktop-sign-in-form"></a>Administradores: Administrar el formulario de inicio de sesión de Power BI Desktop
La primera vez que se inicia Power BI Desktop, aparece un formulario de inicio de sesión. Se puede rellenar la información o iniciar sesión en Power BI para continuar. Los administradores administran este formulario mediante una clave de registro. 

![Formulario de inicio de sesión inicial para Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Los administradores usan la siguiente clave de registro para deshabilitar el formulario de inicio de sesión. Esto también se puede desarrollar en toda la organización mediante directivas globales.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
También puede probar la siguiente clave, que ha funcionado para algunos clientes según sus configuraciones:

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

Un valor de 0 deshabilitará el cuadro de diálogo.




¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

