---
UID: NC:dispmprt.DXGKDDI_GETGPUPARTITIONINFO
title: DXGKDDI_GETGPUPARTITIONINFO
author: windows-driver-content
description: Returns physical GPU partition information.
tech.root: display
ms.assetid: 1355e857-f565-4705-8dde-077bb042bcb3
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_GETGPUPARTITIONINFO callback function"]
f1_keywords:
 - "dispmprt/DXGKDDI_GETGPUPARTITIONINFO"
 - "DXGKDDI_GETGPUPARTITIONINFO"
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
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_GETGPUPARTITIONINFO
targetos: Windows
dev_langs:
 - c++
ms.custom: rs6, 19H1
---

# DXGKDDI_GETGPUPARTITIONINFO callback function

## -description

Returns physical GPU partition information. The DXGKDDI_GETGPUPARTITIONINFO callback function is called once during the graphics adapter initialization.

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


## -remarks

The OS will set a particular partition count (one of the driver returned values) before a first vGPU is created.  Unless the buffer is not large enough, a driver should always set NumGpuPartitionOptions and CurrentGpuPartitionCount, even when returning STATUS_BUFFER_TOO_SMALL.

## -see-also
