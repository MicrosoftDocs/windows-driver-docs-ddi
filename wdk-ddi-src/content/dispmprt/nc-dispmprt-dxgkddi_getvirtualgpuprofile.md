---
UID: NC:dispmprt.DXGKDDI_GETVIRTUALGPUPROFILE
title: DXGKDDI_GETVIRTUALGPUPROFILE
description: Returns information about the vGPU profile, which is supported by the physical GPU when it is divided into given number of partitions.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKDDI_GETVIRTUALGPUPROFILE callback function"]
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
 - DXGKDDI_GETVIRTUALGPUPROFILE
 - dispmprt/DXGKDDI_GETVIRTUALGPUPROFILE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_GETVIRTUALGPUPROFILE
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_GETVIRTUALGPUPROFILE callback function


## -description

Returns information about the vGPU profile, which is supported by the physical GPU when it is divided into given number of partitions. This function could be called multiple times to get current vGPU capabilities.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs 

[in, out] A pointer to the DXGKARG_GETVIRTUALGPUPROFILE structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_GETVIRTUALGPUPROFILE DxgkddiGetvirtualgpuprofile; 

// Definition

NTSTATUS DxgkddiGetvirtualgpuprofile 
(
	HANDLE Context
	DXGKARG_GETVIRTUALGPUPROFILE * pArgs
)
{...}

```

## -remarks

## -see-also

