---
UID: NC:dispmprt.DXGKDDI_GETVIRTUALGPUINFO
title: DXGKDDI_GETVIRTUALGPUINFO
author: windows-driver-content
description: Queries the current capability of a previously created vGPU.
tech.root: display
ms.assetid: d52799c8-a962-4b41-a03c-d1454efb7b88
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "dispmprt/DXGKDDI_GETVIRTUALGPUINFO"
req.header: dispmprt.h
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_GETVIRTUALGPUINFO
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_GETVIRTUALGPUINFO callback function

## -description

Queries the current capability of a previously created vGPU.

## -prototype

```
//Declaration

DXGKDDI_GETVIRTUALGPUINFO DxgkddiGetvirtualgpuinfo; 

// Definition

NTSTATUS DxgkddiGetvirtualgpuinfo 
(
	HANDLE Context
	DXGKARG_GETVIRTUALGPUINFO * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in, out] A pointer to a DXGKARG_GETVIRTUALGPUINFO structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks

## -see-also
