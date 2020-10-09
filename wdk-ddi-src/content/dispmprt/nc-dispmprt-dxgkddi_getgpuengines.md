---
UID: NC:dispmprt.DXGKDDI_GETGPUENGINES
title: DXGKDDI_GETGPUENGINES
description: This function is no longer used and maybe be deleted in the near future.  It is currently required, but will never be called.
tech.root: display
ms.assetid: 2516376d-9fb4-47a5-8178-304f2b549f48
ms.date: 04/04/2019
keywords: ["DXGKDDI_GETGPUENGINES callback function"]
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
ms.custom: 19H1
f1_keywords:
 - DXGKDDI_GETGPUENGINES
 - dispmprt/DXGKDDI_GETGPUENGINES
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_GETGPUENGINES
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_GETGPUENGINES callback function


## -description

This function is no longer used and maybe be deleted in the near future.  It is currently required, but will never be called.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs 

[in] A pointer to the DXGKARG_GETGPUENGINES structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_GETGPUENGINES DxgkddiGetgpuengines; 

// Definition

NTSTATUS DxgkddiGetgpuengines 
(
	HANDLE Context
	DXGKARG_GETGPUENGINES * pArgs
)
{...}

```

## -remarks

## -see-also

