---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET_CAPS_3
title: DXGK_BRIGHTNESS_GET_CAPS_3
author: windows-driver-content
description: 
ms.assetid: 8611cbe1-4c56-4c39-b2a7-41c73262052b
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
-	DXGK_BRIGHTNESS_GET_CAPS_3
product: Windows
targetos: Windows
---

# DXGK_BRIGHTNESS_GET_CAPS_3 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DXGK_BRIGHTNESS_GET_CAPS_3 DxgkBrightnessGetCaps3; 

// Definition

NTSTATUS DxgkBrightnessGetCaps3 
(
	PVOID Context
	ULONG ChildUid
	DXGK_BRIGHTNESS_CAPS *pBrightnessCaps
)
{...}

DXGK_BRIGHTNESS_GET_CAPS_3 


```

## -parameters

### -param Context: 
### -param ChildUid: 
### -param *pBrightnessCaps: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also