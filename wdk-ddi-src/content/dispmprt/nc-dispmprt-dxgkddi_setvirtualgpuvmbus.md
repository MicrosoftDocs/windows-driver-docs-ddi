---
UID: NC:dispmprt.DXGKDDI_SETVIRTUALGPUVMBUS
title: DXGKDDI_SETVIRTUALGPUVMBUS
description: This function passes a kernel mode virtual machine bus handle to the kernel mode driver.
tech.root: display
ms.assetid: ae281f37-bb05-4efe-a8d3-d59e76fe83d6
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_SETVIRTUALGPUVMBUS callback function"]
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
 - DXGKDDI_SETVIRTUALGPUVMBUS
 - dispmprt/DXGKDDI_SETVIRTUALGPUVMBUS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_SETVIRTUALGPUVMBUS
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_SETVIRTUALGPUVMBUS callback function


## -description

This function passes a kernel mode virtual machine bus handle to the kernel mode driver. The handle is used to create VM bus channels for communication between guest and host KMDs.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in, out] A pointer to a DXGKARG_SETVIRTUALGPUVMBUS structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds, STATUS_INVALID_PARAMETER otherwise.

## -prototype

```
//Declaration

DXGKDDI_SETVIRTUALGPUVMBUS DxgkddiSetvirtualgpuvmbus; 

// Definition

NTSTATUS DxgkddiSetvirtualgpuvmbus 
(
	HANDLE Context
	DXGKARG_SETVIRTUALGPUVMBUS * pArgs
)
{...}

```

## -remarks

The kernel mode driver uses the kernel mode handle to create a VM bus channel. The function is called before the guest KMD gets DxgkDdiAddDevice and DxgkDdiStartDevice calls (in case of Windows OS on the guest partition). The function could be called multiple times with a new handle for the same virtual GPU. When this happened it is recommended to destroy the old channel and create the new one.

## -see-also

