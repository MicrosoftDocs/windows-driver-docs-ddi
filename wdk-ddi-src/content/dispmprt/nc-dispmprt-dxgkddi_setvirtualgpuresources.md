---
UID: NC:dispmprt.DXGKDDI_SETVIRTUALGPURESOURCES
title: DXGKDDI_SETVIRTUALGPURESOURCES
description: This function assigns physical resources capabilities to a virtual GPU.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKDDI_SETVIRTUALGPURESOURCES callback function"]
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
 - DXGKDDI_SETVIRTUALGPURESOURCES
 - dispmprt/DXGKDDI_SETVIRTUALGPURESOURCES
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
dev_langs:
 - c++
---

# DXGKDDI_SETVIRTUALGPURESOURCES callback function


## -description

This function assigns physical resources capabilities to a virtual GPU. The function is called before setting the virtual GPU to the D0 state.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in] A pointer to a DXGKARG_SETVIRTUALGPURESOURCES structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

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

## -remarks

Remapping of vGPUs is not currently supported.

## -see-also

