---
UID: NE:d3dkmddi._DXGK_MEMORY_TRANSFER_DIRECTION
title: "_DXGK_MEMORY_TRANSFER_DIRECTION"
author: windows-driver-content
description: DXGK_MEMORY_TRANSFER_DIRECTION is used as part of an allocation transfer operation to specify the direction of the transfer.
old-location: display\dxgk_memory_transfer_direction.htm
old-project: display
ms.assetid: A45411DF-AD08-4349-A134-091343E7989E
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGK_MEMORY_TRANSFER_DIRECTION, DXGK_MEMORY_TRANSFER_DIRECTION enumeration [Display Devices], DXGK_MEMORY_TRANSFER_LOCAL_TO_LOCAL, DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM, DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL, _DXGK_MEMORY_TRANSFER_DIRECTION, d3dkmddi/DXGK_MEMORY_TRANSFER_DIRECTION, d3dkmddi/DXGK_MEMORY_TRANSFER_LOCAL_TO_LOCAL, d3dkmddi/DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM, d3dkmddi/DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL, display.dxgk_memory_transfer_direction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MEMORY_TRANSFER_DIRECTION
product: Windows
targetos: Windows
req.typenames: DXGK_MEMORY_TRANSFER_DIRECTION
---

# _DXGK_MEMORY_TRANSFER_DIRECTION enumeration


## -description


<b>DXGK_MEMORY_TRANSFER_DIRECTION</b> is used as part of an allocation transfer operation to specify the direction of the transfer.




## -enum-fields




### -field DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM

Transfer from local GPU memory to system memory.


### -field DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL

Transfer from system memory to local GPU memory.


### -field DXGK_MEMORY_TRANSFER_LOCAL_TO_LOCAL

Transfer from local GPU memory to local GPU memory.

