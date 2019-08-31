---
UID: NC:dxgiddi.PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB
title: PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB (dxgiddi.h)
description: pfnSubmitPresentToHwQueueCb submits a Present operation to a hardware queue.
ms.assetid: 8201a3f6-ea2f-4dd3-ba74-9f45bbe5bbad
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "dxgiddi/PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB"
req.header: dxgiddi.h
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- dxgiddi.h
api_name: 
- PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB callback function

## -description

pfnSubmitPresentToHwQueueCb submits a Present operation to a hardware queue.

## -prototype

```cpp
//Declaration

PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB PfnddxgiddiSubmitpresenttohwqueuecb; 

// Definition

HRESULT PfnddxgiddiSubmitpresenttohwqueuecb 
(
	HANDLE hDevice
	DXGIDDICB_SUBMITPRESENTTOHWQUEUE *
)
{...}

```

## -parameters

### -param hDevice

A handle to a device.

### -param *

Pointer to a [DXGIDDICB_SUBMITPRESENTTOHWQUEUE](ns-dxgiddi-dxgiddicb_submitpresenttohwqueue.md) structure.



## -returns

Returns HRESULT.

## -remarks



## -see-also
