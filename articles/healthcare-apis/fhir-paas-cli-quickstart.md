---
title: 'Inicio rápido: Implementación de Azure API for FHIR mediante la CLI de Azure'
description: En este inicio rápido va a aprender a implementar Azure API for FHIR en Azure mediante la CLI de Azure.
services: healthcare-apis
author: matjazl
ms.service: healthcare-apis
ms.subservice: fhir
ms.topic: quickstart
ms.date: 10/15/2019
ms.author: cavoeg
ms.custom: devx-track-azurecli
ms.openlocfilehash: 3340cd0a39b0f5311487fec5b05d37e3376d433a
ms.sourcegitcommit: 8e7316bd4c4991de62ea485adca30065e5b86c67
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94659259"
---
# <a name="quickstart-deploy-azure-api-for-fhir-using-azure-cli"></a>Inicio rápido: Implementación de Azure API for FHIR mediante la CLI de Azure

En este inicio rápido va a aprender a implementar Azure API for FHIR en Azure mediante la CLI de Azure.

[!INCLUDE [quickstarts-free-trial-note](../../includes/quickstarts-free-trial-note.md)]

[!INCLUDE [azure-cli-prepare-your-environment.md](../../includes/azure-cli-prepare-your-environment.md)]

## <a name="add-healthcareapis-extension"></a>Incorporación de la extensión HealthcareAPIs

```azurecli-interactive
az extension add --name healthcareapis
```

Obtenga una lista de comandos para HealthcareAPIs:

```azurecli-interactive
az healthcareapis --help
```

## <a name="create-azure-resource-group"></a>Creación del grupo de recursos de Azure

Elija un nombre para el grupo de recursos que contendrá Azure API for FHIR y créelo:

```azurecli-interactive
az group create --name "myResourceGroup" --location westus2
```

## <a name="deploy-the-azure-api-for-fhir"></a>Implementación de Azure API for FHIR

```azurecli-interactive
az healthcareapis create --resource-group myResourceGroup --name nameoffhiraccount --kind fhir-r4 --location westus2 
```

## <a name="fetch-fhir-api-capability-statement"></a>Captura de la instrucción de funcionalidad de la API de FHIR

Obtenga una instrucción de funcionalidad de la API de FHIR con:

```azurecli-interactive
curl --url "https://nameoffhiraccount.azurehealthcareapis.com/metadata"
```

## <a name="clean-up-resources"></a>Limpieza de recursos

Si no va a seguir usando esta aplicación, elimine el grupo de recursos mediante los siguientes pasos:

```azurecli-interactive
az group delete --name "myResourceGroup"
```

## <a name="next-steps"></a>Pasos siguientes

En este inicio rápido, ha implementado Azure API for FHIR en su suscripción. Para establecer opciones de configuración adicionales en Azure API for FHIR, continúe con la guía paso a paso de configuración adicional. Si está listo para empezar a usar Azure API for FHIR, lea más información sobre cómo registrar aplicaciones.

>[!div class="nextstepaction"]
>[Configuración adicional en Azure API for FHIR](azure-api-for-fhir-additional-settings.md)

>[!div class="nextstepaction"]
>[Introducción al registro de aplicaciones](fhir-app-registration.md)
