---
UID: NC:dispmprt.DXGKDDI_GETGPUPARTITIONINFO
title: DXGKDDI_GETGPUPARTITIONINFO
description: Returns physical GPU partition information.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKDDI_GETGPUPARTITIONINFO callback function"]
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: rs6, 19H1
f1_keywords:
 - DXGKDDI_GETGPUPARTITIONINFO
 - dispmprt/DXGKDDI_GETGPUPARTITIONINFO
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_GETGPUPARTITIONINFO
dev_langs:
 - c++
---

# DXGKDDI_GETGPUPARTITIONINFO callback function


## -description

Returns physical GPU partition information. The DXGKDDI_GETGPUPARTITIONINFO callback function is called once during the graphics adapter initialization.

## -parameters

### -param Context

A handle to the driver context.

### -param pArgs

Pointer to a DXGKARG_GETGPUPARTITIONINFO structure that contains arguments.

## -returns

Return one of the following values:

* STATUS_SUCCESS
* STATUS_BUFFER_TOO_SMALL
* If any other return code is specified the GPU will be excluded from partitioning

## -prototype

```
//Declaration

DXGKDDI_GETGPUPARTITIONINFO DxgkddiGetgpupartitioninfo; 

// Definition

NTSTATUS DxgkddiGetgpupartitioninfo 
(
	HANDLE Context
	DXGKARG_GETGPUPARTITIONINFO * pArgs
)
{...}

```

## -remarks

The OS will set a particular partition count (one of the driver returned values) before a first vGPU is created.  Unless the buffer is not large enough, a driver should always set NumGpuPartitionOptions and CurrentGpuPartitionCount, even when returning STATUS_BUFFER_TOO_SMALL.

## -see-also

