---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061
title: PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061
description: Returns the driver for the video extension object size.
tech.root: display
ms.date: 04/04/2019
keywords: ["PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061 callback function


## -description

Returns the driver for the video extension object size. Direct3D runtime allocates space for this driver object. On creation, the driver places the object into the allocation that was provided by the runtime.

## -parameters

### -param hDrvDevice

Handle for the D3D12 device.

### -param pArgs

Pointer to a [D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063](ns-d3d12umddi-d3d12ddiarg_create_video_extension_command_0063.md) structure.

## -returns

Returns SIZE_T.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061 Pfnd3d12ddiCalcprivatevideoextensioncommandsize0061; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatevideoextensioncommandsize0061 
(
	D3D12DDI_HDEVICE hDrvDevice
	 const D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063 *pArgs
)
{...}

```

## -remarks

## -see-also

