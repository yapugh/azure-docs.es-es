---
title: Compatibilidad para usar Azure Site Recovery con Azure Backup
description: Proporciona información general sobre cómo Azure Site Recovery y Azure Backup se pueden usar conjuntamente.
author: sideeksh
manager: rochakm
ms.service: site-recovery
ms.topic: conceptual
ms.date: 10/15/2019
ms.author: sideeksh
ms.openlocfilehash: c334eee34eb878135d3d81ab15d03618c6604846
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "86135182"
---
# <a name="support-for-using-site-recovery-with-azure-backup"></a>Compatibilidad para usar Site Recovery con Azure Backup

En este artículo se resume la compatibilidad para usar el [servicio Site Recovery](site-recovery-overview.md) junto con el [servicio Azure Backup](../backup/backup-overview.md).

**Acción** | **Compatibilidad de Site Recovery** | **Detalles**
--- | --- | ---
**Implementación conjunta de servicios** | Compatible | Los servicios son interoperables y se pueden configurar juntos.
**Copia de seguridad/restauración de archivos** | Compatible | Cuando la copia de seguridad y la replicación están habilitadas para una VM y se realizan copias de seguridad, no hay ningún problema en la restauración de archivos en las VM de origen ni en el grupo de VM. La replicación continúa como de costumbre sin ningún cambio en el estado de la replicación.
**Restauración de disco** | No compatible actualmente | Si restaura un disco del que se ha realizado una copia de seguridad, deberá deshabilitar la replicación y luego volver a habilitarla para la máquina virtual.
**Restauración de máquina virtual** | No compatible actualmente | Si restaura una máquina virtual o un grupo de máquinas virtuales, deberá deshabilitar y volver a habilitar la replicación para la máquina virtual.  


