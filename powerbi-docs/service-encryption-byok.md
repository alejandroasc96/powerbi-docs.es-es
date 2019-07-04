---
title: Traiga sus propias claves de cifrado para Power BI (versión preliminar)
description: Aprenda a usar sus propias claves de cifrado en Power BI Premium.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/18/2019
LocalizationGroup: Premium
ms.openlocfilehash: 5c93a50ce481c5fad899c1911b30100dca7cb841
ms.sourcegitcommit: 8c52b3256f9c1b8e344f22c1867e56e078c6a87c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2019
ms.locfileid: "67264503"
---
# <a name="bring-your-own-encryption-keys-for-power-bi-preview"></a>Traiga sus propias claves de cifrado para Power BI (versión preliminar)

Power BI cifra los datos _en reposo_ y _en proceso_. De forma predeterminada, Power BI usa claves administradas por Microsoft para cifrar los datos. En Power BI Premium también puede usar sus propias claves para datos en reposo que se importan en un conjunto de datos (consulte [Consideraciones sobre el origen de datos y el almacenamiento](#data-source-and-storage-considerations) para más información). Este enfoque suele describirse como _Bring Your Own Key_ (BYOK).

## <a name="why-use-byok"></a>¿Por qué usar BYOK?

BYOK permite satisfacer más fácilmente los requisitos de cumplimiento que especifican las condiciones de las claves con el proveedor de servicios en la nube (en este caso de Microsoft). Con BYOK, puede proporcionar y controlar las claves de cifrado para los datos en reposo de Power BI en el nivel de aplicación. Como resultado, puede ejercer el control y revocar las claves de la organización si decide dejar el servicio. Al revocar las claves, los datos son ilegibles para el servicio.

## <a name="data-source-and-storage-considerations"></a>Consideraciones sobre el origen de datos y el almacenamiento

Para usar BYOK, debe cargar los datos en el servicio Power BI desde un archivo de Power BI Desktop (PBIX). No se puede usar BYOK en los siguientes escenarios:

- Conexiones dinámicas de Analysis Services
- Libros de Excel (a menos que los datos se importen primero en Power BI Desktop)
- Conjuntos de datos de inserción

BYOK solo se aplica al conjunto de datos asociado al archivo PBIX, no a las memorias caché de resultados de consultas de iconos y objetos visuales.

## <a name="configure-azure-key-vault"></a>Configuración de Azure Key Vault

En esta sección se enseña cómo configurar Azure Key Vault, una herramienta para almacenar y acceder a los secretos, como las claves de cifrado, de forma segura. Puede usar un almacén de claves existente para almacenar las claves de cifrado o puede crear uno nuevo específicamente para su uso con Power BI.

Las instrucciones de esta sección presuponen un conocimiento básico de Azure Key Vault. Para más información, consulte [¿Qué es Azure Key Vault?](/azure/key-vault/key-vault-whatis). Configure el almacén de claves de la manera siguiente:

1. Agregue el servicio Power BI como una entidad de servicio en el almacén de claves con permisos para encapsular y desencapsular.

1. Cree una clave RSA con una longitud de 4096 bits (o use una clave existente de este tipo), con permisos para encapsular y desencapsular.

1. Recomendado: Compruebe que el almacén de claves tiene la opción de _eliminación temporal_ habilitada.

### <a name="add-the-service-principal"></a>Adición de la entidad de servicio

1. En Azure Portal, en el almacén de claves, en **Directivas de acceso**, seleccione **Agregar nueva**.

1. En **Seleccionar entidad**, busque y seleccione Microsoft.Azure.AnalysisServices.

1. En **Permisos de clave**, seleccione **Desencapsular clave** y **Encapsular clave**.

    ![Componentes del archivo PBIX](media/service-encryption-byok/service-principal.png)

1. Seleccione **Aceptar** y, a continuación, seleccione **Guardar**.

### <a name="create-an-rsa-key"></a>Creación de una clave RSA

1. En el almacén de claves, en **Claves**, seleccione **Generar/Importar**.

1. En **Tipo de clave**, seleccione RSA y en **Tamaño de la clave RSA**, seleccione 4096.

    ![Componentes del archivo PBIX](media/service-encryption-byok/create-rsa-key.png)

1. Seleccione **Crear**.

1. En **Claves**, seleccione la clave que creó.

1. Seleccione el identificador GUID de la **Versión actual** de la clave.

1. Compruebe que están seleccionados **Encapsular clave** y **Desencapsular clave**. Copie el **Identificador de clave** que se va a usar al habilitar BYOK en Power BI.

    ![Componentes del archivo PBIX](media/service-encryption-byok/key-properties.png)

### <a name="soft-delete-option"></a>Opción de eliminación temporal

Se recomienda que habilite la [eliminación temporal](/azure/key-vault/key-vault-ovw-soft-delete) en el almacén de claves para protegerse frente a la pérdida de datos en el caso de eliminación accidental de la clave o el almacén de claves. Debe usar [PowerShell para habilitar la propiedad de "eliminación temporal"](/azure/key-vault/key-vault-soft-delete-powershell) en el almacén de claves, ya que esta opción aún no está disponible en Azure Portal.

Con Azure Key Vault configurado correctamente, está listo para habilitar BYOK en el inquilino.

## <a name="enable-byok-on-your-tenant"></a>Habilitación de BYOK en el inquilino

Para habilitar BYOK con [PowerShell](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt.Admin) en el nivel de inquilino, primero debe proporcionar en el inquilino de Power BI las claves de cifrado que ha creado y almacenado en Azure Key Vault. A continuación, debe asignar estas claves de cifrado en la capacidad Premium para cifrar el contenido de esta capacidad.

### <a name="important-considerations"></a>Consideraciones importantes

Antes de habilitar BYOK, tenga en cuenta las consideraciones siguientes:

- Actualmente no se puede deshabilitar BYOK después de habilitarlo. En función de cómo se especifiquen los parámetros de `Add-PowerBIEncryptionKey`, puede controlar cómo usar BYOK para una o varias de las capacidades. Sin embargo, no se puede deshacer la introducción de claves en el inquilino. Para más información, consulte [Habilitación de BYOK](#enable-byok).

- No se puede mover _directamente_ un área de trabajo que usa BYOK desde una capacidad dedicada de Power BI Premium a una capacidad compartida. Debe mover primero el área de trabajo a una capacidad dedicada que no tenga habilitado BYOK.

### <a name="enable-byok"></a>Habilitación de BYOK

Para habilitar BYOK, debe ser un administrador del inquilino del servicio Power BI y haber iniciado sesión con el cmdlet `Connect-PowerBIServiceAccount`. A continuación, utilice [`Add-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/Add-PowerBIEncryptionKey) para habilitar BYOK, tal como se muestra en el ejemplo siguiente:

```powershell
Add-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
```

El cmdlet acepta dos parámetros de modificador que afectan al cifrado de las capacidades actuales y futuras. Ninguno de los modificadores está establecido de forma predeterminada:

- `-Activate`: indica que esta clave se usará para todas las capacidades existentes en el inquilino.

- `-Default`: indica que esta clave es ahora la predeterminada para todo el inquilino. Cuando se crea una nueva capacidad, dicha capacidad hereda esta clave.

Si especifica `-Default`, todas las capacidades creadas en este inquilino desde este momento se cifrarán con la clave especificada (o una clave predeterminada actualizada). No se puede deshacer la operación predeterminada, por lo que se pierde la opción de crear una capacidad Premium que no use BYOK en el inquilino.

Tiene el control sobre el uso de BYOK en el inquilino. Por ejemplo, para cifrar una sola capacidad, llame a `Add-PowerBIEncryptionKey` sin `-Activate` o `-Default`. A continuación, llame a `Set-PowerBICapacityEncryptionKey` para la capacidad en la que desea habilitar BYOK.

## <a name="manage-byok"></a>Administración de BYOK

Power BI proporciona cmdlets adicionales para ayudar a administrar BYOK en el inquilino:

- Utilice [`Get-PowerBICapacity`](/powershell/module/microsoftpowerbimgmt.capacities/get-powerbicapacity) para obtener la clave que usa actualmente una capacidad:

    ```powershell
    Get-PowerBICapacity -Scope Organization -ShowEncryptionKey
    ```

- Utilice [`Get-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiencryptionkey) para obtener la clave que usa actualmente el inquilino:

    ```powershell
    Get-PowerBIEncryptionKey
    ```

- Utilice [`Get-PowerBIWorkspaceEncryptionStatus`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiworkspaceencryptionstatus) para ver si se cifran los conjuntos de datos de un área de trabajo y si el estado de cifrado está sincronizado con el área de trabajo:

    ```powershell
    Get-PowerBIWorkspaceEncryptionStatus -Name'Contoso Sales'
    ```

    Tenga en cuenta que el cifrado se habilita en el nivel de capacidad, pero el estado de cifrado se obtiene en el nivel de conjunto de datos del área de trabajo especificada.

- Utilice [`Set-PowerBICapacityEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/set-powerbicapacityencryptionkey) para actualizar la clave de cifrado de la capacidad de Power BI:

    ```powershell
    Set-PowerBICapacityEncryptionKey-CapacityId 08d57fce-9e79-49ac-afac-d61765f97f6f -KeyName 'Contoso Sales'
    ```

- Utilice [`Switch-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/switch-powerbiencryptionkey) para cambiar (o _rotar_) la versión de la clave que se usa para el cifrado. El cmdlet simplemente actualiza el valor de `-KeyVaultKeyUri` de la clave especificada en la opción `-Name`:

    ```powershell
    Switch-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
    ```