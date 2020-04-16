---
UID: NC:dispmprt.DXGKDDI_SETVIRTUALGPURESOURCES
title: DXGKDDI_SETVIRTUALGPURESOURCES
author: windows-driver-content
description: This function assigns physical resources capabilities to a virtual GPU.
tech.root: display
ms.assetid: fd5896b3-0db1-497d-a984-5e05a293626d
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_SETVIRTUALGPURESOURCES callback function"]
f1_keywords:
 - "dispmprt/DXGKDDI_SETVIRTUALGPURESOURCES"
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
 - DXGKDDI_SETVIRTUALGPURESOURCES
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_SETVIRTUALGPURESOURCES callback function

## -description

This function assigns physical resources capabilities to a virtual GPU. The function is called before setting the virtual GPU to the D0 state.

## -prototype

```
//Declaration

DXGKDDI_SETVIRTUALGPURESOURCES DxgkddiSetvirtualgpuresources; 

// Definition

NTSTATUS DxgkddiSetvirtualgpuresources 
(
	HANDLE Context
	DXGKARG_SETVIRTUALGPURESOURCES * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in] A pointer to a DXGKARG_SETVIRTUALGPURESOURCES structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks


Remapping of vGPUs is not currently supported.

## -see-also
