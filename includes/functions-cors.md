---
author: ggailey777
ms.service: azure-functions
ms.topic: include
ms.date: 05/06/2020
ms.author: glenga
ms.openlocfilehash: a5f829fc0e153c3a427fd1c7cc7d5c613cd624f6
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "83648250"
---
Azure Functions admite el uso compartido de recursos entre orígenes (CORS). CORS se configura [en el portal](../articles/azure-functions/functions-how-to-use-azure-function-app-settings.md#cors) y mediante la [CLI de Azure](/cli/azure/functionapp/cors). La lista de orígenes permitidos de CORS se aplica en el nivel de la aplicación de función. Con CORS habilitado, las respuestas incluyen el encabezado `Access-Control-Allow-Origin`. Para obtener más información, consulte [Uso compartido de recursos entre orígenes](../articles/azure-functions/functions-how-to-use-azure-function-app-settings.md#cors). 