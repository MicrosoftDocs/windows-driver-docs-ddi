---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDQUEUE_0001
title: PFND3D12DDI_CREATECOMMANDQUEUE_0001
author: windows-driver-content
description: The PFND3D12DDI_CREATECOMMANDQUEUE_0001 callback function is used to create command queue.
ms.assetid: 872fcefc-ef32-443f-acd2-f5a206abee33
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CREATECOMMANDQUEUE_0001
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATECOMMANDQUEUE_0001 callback function

## -description

The PFND3D12DDI_CREATECOMMANDQUEUE_0001 callback function is used to create command queue.

## -prototype

```
//Declaration

PFND3D12DDI_CREATECOMMANDQUEUE_0001 Pfnd3d12ddiCreatecommandqueue0001; 

// Definition

HRESULT Pfnd3d12ddiCreatecommandqueue0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATECOMMANDQUEUE_0001 *
)
{...}

PFND3D12DDI_CREATECOMMANDQUEUE_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE

The handle of a device.

### -param *

Arguments used to create a command queue.



## -returns

Returns HRESULT.

## -remarks

Access this callback function by using a device functions core structure, such as the [D3D12DDI_DEVICE_FUNCS_CORE_0010](ns-d3d12umddi-d3d12ddi_device_funcs_core_0010.md) structure.


## -see-also