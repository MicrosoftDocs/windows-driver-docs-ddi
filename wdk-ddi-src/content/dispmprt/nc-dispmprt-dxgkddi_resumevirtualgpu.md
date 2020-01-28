---
UID: NC:dispmprt.DXGKDDI_RESUMEVIRTUALGPU
title: DXGKDDI_RESUMEVIRTUALGPU
author: windows-driver-content
description: Virtual GPU suspend/resume is not supported.
tech.root: display
ms.assetid: 00d56e84-4997-4ea5-868b-bd85fa6d3926
ms.author: windowsdriverdev
ms.date: 04/04/2019
f1_keywords:
 - "dispmprt/DXGKDDI_RESUMEVIRTUALGPU"
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
 - DXGKDDI_RESUMEVIRTUALGPU
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_RESUMEVIRTUALGPU callback function

## -description

> [!NOTE]
> Virtual GPU suspend/resume is not supported. This callback function is never used.

Resumes execution of processing engines of the given virtual GPU.

## -prototype

```
//Declaration

DXGKDDI_RESUMEVIRTUALGPU DxgkddiResumevirtualgpu; 

// Definition

NTSTATUS DxgkddiResumevirtualgpu 
(
	HANDLE Context
	DXGKARG_RESUMEVIRTUALGPU * pArgs
)
{...}

```

## -parameters



### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in] A pointer to a DXGKARG_RESUMEVIRTUALGPU structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks




## -see-also
