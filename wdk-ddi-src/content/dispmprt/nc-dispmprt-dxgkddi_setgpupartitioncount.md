---
UID: NC:dispmprt.DXGKDDI_SETGPUPARTITIONCOUNT
title: DXGKDDI_SETGPUPARTITIONCOUNT
author: windows-driver-content
description: Sets the number of partitions the physical GPU should be divided into.
tech.root: display
ms.assetid: c6e2a5ee-45e5-4cd3-82e9-64b74f092799
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "dispmprt/DXGKDDI_SETGPUPARTITIONCOUNT"
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
 - DXGKDDI_SETGPUPARTITIONCOUNT
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# DXGKDDI_SETGPUPARTITIONCOUNT callback function

## -description

Sets the number of partitions the physical GPU should be divided into. The OS guarantees that at this point there are no existing vGPUs on the physical GPU.

## -prototype

```
//Declaration

DXGKDDI_SETGPUPARTITIONCOUNT DxgkddiSetgpupartitioncount; 

// Definition

NTSTATUS DxgkddiSetgpupartitioncount 
(
	HANDLE Context
	DXGKARG_SETGPUPARTITIONCOUNT * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in] A pointer to a DXGKARG_SETGPUPARTITIONCOUNT structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks




## -see-also
