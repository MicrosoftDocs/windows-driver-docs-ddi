---
UID: NC:dispmprt.DXGKDDI_CREATEVIRTUALGPU
title: DXGKDDI_CREATEVIRTUALGPU
description: This function creates a virtual GPU with provided parameters and re-tunes information about physical GPU resources, which are needed for the virtual GPU.
tech.root: display
ms.assetid: fd92587b-1513-4e31-91d4-4f2a9f1eeb14
ms.date: 04/04/2019
keywords: ["DXGKDDI_CREATEVIRTUALGPU callback function"]
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
 - DXGKDDI_CREATEVIRTUALGPU
 - dispmprt/DXGKDDI_CREATEVIRTUALGPU
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_CREATEVIRTUALGPU
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_CREATEVIRTUALGPU callback function


## -description

This function creates a virtual GPU with provided parameters and re-tunes information about physical GPU resources, which are needed for the virtual GPU.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in] Pointer to a [DXGKARG_CREATEVIRTUALGPU](ns-dispmprt-_dxgkarg_createvirtualgpu.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_CREATEVIRTUALGPU DxgkddiCreatevirtualgpu; 

// Definition

NTSTATUS DxgkddiCreatevirtualgpu 
(
	HANDLE Context
	DXGKARG_CREATEVIRTUALGPU * pArgs
)
{...}

```

## -remarks

## -see-also

