---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEHWQUEUE_CB_0050
title: PFND3D12DDI_CREATEHWQUEUE_CB_0050 (d3d12umddi.h)
description: Creates a hardware queue associated with a command queue.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATEHWQUEUE_CB_0050 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CREATEHWQUEUE_CB_0050
 - d3d12umddi/PFND3D12DDI_CREATEHWQUEUE_CB_0050
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEHWQUEUE_CB_0050
dev_langs:
 - c++
---

# PFND3D12DDI_CREATEHWQUEUE_CB_0050 callback function


## -description

Creates a hardware queue associated with a command queue.

## -parameters

### -param hRTCommandQueue

The handle of the command queue for the driver to use when it calls back into the runtime.

### -param unnamedParam2

Pointer to a [D3DDDICB_CREATEHWQUEUE](../d3dumddi/ns-d3dumddi-_d3dddicb_createhwqueue.md) structure that contains information needed to create a hardware queue.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEHWQUEUE_CB_0050 Pfnd3d12ddiCreatehwqueueCb0050; 

// Definition

HRESULT Pfnd3d12ddiCreatehwqueueCb0050 
(
	D3D12DDI_HRTCOMMANDQUEUE hRTCommandQueue
	D3DDDICB_CREATEHWQUEUE *
)
{...}

```

## -remarks

Destroys are not provided for these objects, as their lifetime is completely managed by the owning runtime object.
Validation will be in place that hardware queue creation must be done against a context either associated with the same command queue, or with a parent scheduling group. The driver is allowed to create hardware queues which reference both types of contexts for a single [CreateCommandQueue](nc-d3d12umddi-pfnd3d12ddi_createcommandqueue_0050.md). The CreateCommandQueue callback is reviewed so the driver is informed of this relationship.

## -see-also

