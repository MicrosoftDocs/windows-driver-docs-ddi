---
UID: NC:dispmprt.DXGKDDI_DESTROYVIRTUALGPU
title: DXGKDDI_DESTROYVIRTUALGPU
author: windows-driver-content
description: The DxgkDdiDestroyVirtualGpu function destroys a previously created virtual GPU.
tech.root: display
ms.assetid: 3c27b27a-265d-4a6e-ac2b-bb8998d2c3b8
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_DESTROYVIRTUALGPU callback function"]
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
targetos: Windows
ms.custom: rs6, 19H1
f1_keywords:
 - DXGKDDI_DESTROYVIRTUALGPU
 - dispmprt/DXGKDDI_DESTROYVIRTUALGPU
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_DESTROYVIRTUALGPU
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_DESTROYVIRTUALGPU callback function


## -description

The DxgkDdiDestroyVirtualGpu function destroys a previously created virtual GPU.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in] Pointer to a [DXGKARG_DESTROYVIRTUALGPU](ns-dispmprt-_dxgkarg_destroyvirtualgpu.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_DESTROYVIRTUALGPU DxgkddiDestroyvirtualgpu; 

// Definition

NTSTATUS DxgkddiDestroyvirtualgpu 
(
	HANDLE Context
	DXGKARG_DESTROYVIRTUALGPU * pArgs
)
{...}

```

## -remarks

## -see-also

