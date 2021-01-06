---
UID: NC:dxgiddi.PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB
title: PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB (dxgiddi.h)
description: pfnSubmitPresentToHwQueueCb submits a Present operation to a hardware queue.
ms.date: 10/19/2018
keywords: ["PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB
 - dxgiddi/PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dxgiddi.h
api_name:
 - PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB
dev_langs:
 - c++
---

# PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB callback function


## -description

pfnSubmitPresentToHwQueueCb submits a Present operation to a hardware queue.

## -parameters

### -param hDevice

A handle to a device.

### -param 

Pointer to a [DXGIDDICB_SUBMITPRESENTTOHWQUEUE](ns-dxgiddi-dxgiddicb_submitpresenttohwqueue.md) structure.

## -returns

Returns HRESULT.

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

## -remarks

## -see-also

