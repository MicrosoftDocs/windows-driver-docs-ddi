---
UID: NE:d3d12umddi.D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS
title: D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS
author: windows-driver-content
description: Defines command queue creation options.
old-location: display\d3d12ddi_command_queue_creation_flags.htm
old-project: display
ms.assetid: 6BA4B1B4-07D6-4498-BDA4-C559FB3E8843
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS enumeration [Display Devices], D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_GLOBAL_REALTIME_PRIORITY, d3d12umddi/D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_GLOBAL_REALTIME_PRIORITY, d3d12umddi/D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_NONE, display.d3d12ddi_command_queue_creation_flags, D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_NONE, d3d12umddi/D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS, D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS
---

# D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS enumeration


## -description


Defines command queue creation options. 


## -syntax


````
typedef enum D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS { 
  D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_NONE                      = 0x00000000,
  D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_GLOBAL_REALTIME_PRIORITY  = 0x00000001
} D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS;
````


## -enum-fields




### -field D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_NONE

Create queue with default value.


### -field D3D12DDI_COMMAND_QUEUE_CREATION_FLAG_GLOBAL_REALTIME_PRIORITY

Requires global real-time priority.

