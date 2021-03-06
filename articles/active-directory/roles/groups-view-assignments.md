---
title: Visualización de los roles asignados a un grupo en Azure Active Directory | Microsoft Docs
description: Obtenga información sobre cómo se pueden ver los roles asignados a un grupo mediante el centro de administración de Azure AD. La visualización de los grupos y los roles asignados son los permisos de usuario predeterminados.
services: active-directory
author: curtand
manager: daveba
ms.service: active-directory
ms.workload: identity
ms.subservice: roles
ms.topic: article
ms.date: 11/05/2020
ms.author: curtand
ms.reviewer: vincesm
ms.custom: it-pro
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8fdfd99b2ef5c1578bc9e87534461d68398c9f6
ms.sourcegitcommit: 0d171fe7fc0893dcc5f6202e73038a91be58da03
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93378285"
---
# <a name="view-roles-assigned-to-a-group-in-azure-active-directory"></a>Visualización de los roles asignados a un grupo en Azure Active Directory

En esta sección se describe cómo se pueden ver los roles asignados a un grupo mediante el centro de administración de Azure AD. La visualización de los grupos y los roles asignados son los permisos de usuario predeterminados.

1. Inicie sesión en el [centro de administración de Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) con credenciales que no sean de administrador o que sí lo sean.

1. Seleccione el grupo que le interese.

1. Seleccione **Roles asignados**. Así podrá ver todos los roles de Azure AD asignados a este grupo.

   ![Visualización de todos los roles asignados a un grupo seleccionado](./media/groups-view-assignments/view-assignments.png)

## <a name="using-powershell"></a>Usar PowerShell

### <a name="get-object-id-of-the-group"></a>Obtención del id. de objeto del grupo

```powershell
Get-AzureADMSGroup -SearchString “Contoso_Helpdesk_Administrators”
```

### <a name="view-role-assignment-to-a-group"></a>Visualización de la asignación de roles a un grupo

```powershell
Get-AzureADMSRoleAssignment -Filter "principalId eq '<object id of group>" 
```

## <a name="using-microsoft-graph-api"></a>Uso de Microsoft Graph API

### <a name="get-object-id-of-the-group"></a>Obtención del id. de objeto del grupo

```powershell
GET https://graph.microsoft.com/beta/groups?$filter displayName eq ‘Contoso_Helpdesk_Administrator’ 
```

### <a name="get-role-assignments-to-a-group"></a>Obtención de la asignación de roles a un grupo

```powershell
GET https://graph.microsoft.com/beta/roleManagement/directory/roleAssignments?$filter=principalId eq
```

## <a name="next-steps"></a>Pasos siguientes

- [Uso de grupos en la nube para administrar asignaciones de roles](groups-concept.md)
- [Solución de problemas de roles asignados a grupos en la nube](groups-faq-troubleshooting.md)
