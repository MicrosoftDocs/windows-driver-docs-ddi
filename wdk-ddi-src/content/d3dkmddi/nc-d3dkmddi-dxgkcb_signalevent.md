---
UID: NC:d3dkmddi.DXGKCB_SIGNALEVENT
title: DXGKCB_SIGNALEVENT (d3dkmddi.h)
description: Allows the kernel mode on the host to signal an event, which is created in the guest during paravirtualization.
ms.assetid: fbb456a6-4ffc-4d65-a3d6-e3d78b573ae3
ms.date: 10/19/2018
keywords: ["DXGKCB_SIGNALEVENT callback function"]
f1_keywords:
 - "d3dkmddi/DXGKCB_SIGNALEVENT"
 - "DXGKCB_SIGNALEVENT"
req.header: d3dkmddi.h
req.include-header: d3dkmddi.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
- d3dkmddi.h
api_name: 
- DXGKCB_SIGNALEVENT
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# DXGKCB_SIGNALEVENT callback function

## -description

Allows the kernel mode on the host to signal an event, which is created in the guest during paravirtualization.

Note that the callback can be used to signal events of the  host processes as well.

## -prototype

```cpp
//Declaration

DXGKCB_SIGNALEVENT DxgkcbSignalevent; 

// Definition

NTSTATUS DxgkcbSignalevent 
(
)
{...}

```

## -parameters

### -param 

Pointer to a [DXGKCB_SIGNALEVENT](ns-d3dkmddi-_dxgkargcb_signalevent.md) structure that contains arguments for this call.

## -returns

Returns NTSTATUS.

## -remarks

The callback must be called on less than DISPATCH_LEVEL level.

The driver must call the callback with the *LastUse* flag during process or device cleanup.

In the case of paravirtualization, the callback does not signal the event synchronously, so the event is not signaled when the callback returns. Otherwise, the event is signaled synchronously.

## -see-also
