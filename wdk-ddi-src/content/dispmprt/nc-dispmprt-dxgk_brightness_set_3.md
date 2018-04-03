---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_3
title: DXGK_BRIGHTNESS_SET_3
author: windows-driver-content
description: 
ms.assetid: 8466303f-b811-43e0-91e2-4322a5f3fa83
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	dispmprt.h
apiname: 
-	DXGK_BRIGHTNESS_SET_3
product: Windows
targetos: Windows
---

# DXGK_BRIGHTNESS_SET_3 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DXGK_BRIGHTNESS_SET_3 DxgkBrightnessSet3; 

// Definition

NTSTATUS DxgkBrightnessSet3 
(
	PVOID Context
	ULONG ChildUid
	PDXGK_BRIGHTNESS_SET_IN pIn
)
{...}

DXGK_BRIGHTNESS_SET_3 


```

## -parameters

### -param Context: 
### -param ChildUid: 
### -param pIn: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also