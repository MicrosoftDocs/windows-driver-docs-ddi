---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020
title: D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020
author: windows-driver-content
description: Command queue functions for video.
old-location: display\d3d12ddi_command_queue_funcs_video.htm
old-project: display
ms.assetid: 3B1FDF51-8B5E-4DF9-BFEC-91FD1A1DEC63
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020, D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020 structure [Display Devices], E, F, I, M, N, O, Q, S, U, V, _, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020, display.d3d12ddi_command_queue_funcs_video"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020
---

# D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020 structure


## -description


Command queue functions for video.


## -syntax


````
typedef struct D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020 {
  PFND3D12DDI_EXECUTECOMMANDLISTS pfnExecuteCommandLists;
  PFND3D12DDI_UPDATETILEMAPPINGS  pfnUpdateTileMappings;
  PFND3D12DDI_COPYTILEMAPPINGS    pfnCopyTileMappings;
  PFND3D12DDI_SIGNAL_FENCE        pfnSignalFence;
  PFND3D12DDI_WAIT_FOR_FENCE      pfnWaitForFence;
} D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020;
````


## -struct-fields




### -field pfnExecuteCommandLists

Execute command lists.


### -field pfnUpdateTileMappings

Update tile mappings.


### -field pfnCopyTileMappings

Copy tile mappings.


### -field pfnSignalFence

Signal fence.


### -field pfnWaitForFence

Wait for fence. 

