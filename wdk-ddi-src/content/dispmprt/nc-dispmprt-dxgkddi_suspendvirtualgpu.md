---
UID: NC:dispmprt.DXGKDDI_SUSPENDVIRTUALGPU
title: DXGKDDI_SUSPENDVIRTUALGPU
author: windows-driver-content
description: Virtual GPU suspend/resume is not supported.
tech.root: display
ms.assetid: a4433fed-25d6-4002-b4f3-a7bfebcce44d
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
 - DXGKDDI_SUSPENDVIRTUALGPU
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# DXGKDDI_SUSPENDVIRTUALGPU callback function

## -description

> [!NOTE]
> Virtual GPU suspend/resume is not supported. This callback function is never used.

This function suspends execution of all engines and operation of the given virtual GPU. The video memory must not be touched after this point.

## -prototype

```
//Declaration

DXGKDDI_SUSPENDVIRTUALGPU DxgkddiSuspendvirtualgpu; 

// Definition

NTSTATUS DxgkddiSuspendvirtualgpu 
(
	HANDLE Context
	DXGKARG_SUSPENDVIRTUALGPU * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in] A pointer to a DXGKARG_SUSPENDVIRTUALGPU structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks




## -see-also
