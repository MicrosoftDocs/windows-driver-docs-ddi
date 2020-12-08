---
UID: NC:dxgiddi.PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB
title: PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB (dxgiddi.h)
description: Implemented by the client driver to submit a present Blt to hardware queue.
ms.date: 10/19/2018
keywords: ["PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB callback function"]
req.header: dxgiddi.h
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
tech.root: display
f1_keywords:
 - PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB
 - dxgiddi/PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dxgiddi.h
api_name:
 - PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB
product:
 - Windows
---

# PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB callback function


## -description

Implemented by the client driver to submit a present Blt to hardware queue.

## -parameters

### -param hDevice

A handle to the device.

### -param DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE *

Pointer to a [DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE](ns-dxgiddi-dxgiddicb_submitpresentblttohwqueue.md) structure that contains information to submit a present Blt to hardware queue.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB PfnddxgiddiSubmitpresentblttohwqueuecb;

// Definition

HRESULT PfnddxgiddiSubmitpresentblttohwqueuecb
(
	HANDLE hDevice
	DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE *
)
{...}

PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB


```

