---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3
title: DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3
author: windows-driver-content
description: 
ms.assetid: 07bffb8b-08d5-4f24-bdf3-c3a4648e8724
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
-	DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3
product: Windows
targetos: Windows
---

# DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3 DxgkBrightnessSetBacklightOptimization3; 

// Definition

NTSTATUS DxgkBrightnessSetBacklightOptimization3 
(
	PVOID Context
	ULONG ChildUid
	DXGK_BACKLIGHT_OPTIMIZATION_LEVEL OptimizationLevel
)
{...}

DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3 


```

## -parameters

### -param Context: 
### -param ChildUid: 
### -param OptimizationLevel: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also