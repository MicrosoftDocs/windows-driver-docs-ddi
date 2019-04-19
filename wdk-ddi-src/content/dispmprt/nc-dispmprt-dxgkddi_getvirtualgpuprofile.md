---
UID: NC:dispmprt.DXGKDDI_GETVIRTUALGPUPROFILE
title: DXGKDDI_GETVIRTUALGPUPROFILE
author: windows-driver-content
description: Returns information about the vGPU profile, which is supported by the physical GPU when it is divided into given number of partitions.
tech.root: display
ms.assetid: b1540828-63bb-491d-b0e0-c54089ffd85f
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
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
 - DXGKDDI_GETVIRTUALGPUPROFILE
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# DXGKDDI_GETVIRTUALGPUPROFILE callback function

## -description

Returns information about the vGPU profile, which is supported by the physical GPU when it is divided into given number of partitions. This function could be called multiple times to get current vGPU capabilities.

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

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs 

[in, out] A pointer to the DXGKARG_GETVIRTUALGPUPROFILE structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks




## -see-also
