---
UID: NC:d3dumddi.PFND3DDDI_SUBMITPRESENTTOHWQUEUECB
title: PFND3DDDI_SUBMITPRESENTTOHWQUEUECB (d3dumddi.h)
description: pfnSubmitPresentToHwQueueCb is invoked by user mode drivers to submit a Blt Present operation to a hardware queue.
ms.assetid: 78923ae5-c07f-465c-a171-7da4743ce4bc
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dumddi.h
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
- d3dumddi.h
api_name: 
- PFND3DDDI_SUBMITPRESENTTOHWQUEUECB
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3DDDI_SUBMITPRESENTTOHWQUEUECB callback function

## -description

pfnSubmitPresentToHwQueueCb is invoked by user mode drivers to submit a Blt Present operation to a hardware queue.

## -prototype

```cpp
//Declaration

PFND3DDDI_SUBMITPRESENTTOHWQUEUECB Pfnd3dddiSubmitpresenttohwqueuecb; 

// Definition

HRESULT Pfnd3dddiSubmitpresenttohwqueuecb 
(
	HANDLE hDevice
	D3DDDICB_SUBMITPRESENTTOHWQUEUE *
)
{...}

```

## -parameters

### -param hDevice

A handle to a device.

### -param *

Pointer to a [D3DDDICB_SUBMITPRESENTTOHWQUEUE](ns-d3dumddi-_d3dddicb_submitpresenttohwqueue.md) structure.

## -returns

Returns HRESULT.

## -remarks




## -see-also
