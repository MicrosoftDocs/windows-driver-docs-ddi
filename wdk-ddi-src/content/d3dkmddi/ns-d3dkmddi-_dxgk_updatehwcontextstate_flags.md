---
UID: NS:d3dkmddi._DXGK_UPDATEHWCONTEXTSTATE_FLAGS
title: "_DXGK_UPDATEHWCONTEXTSTATE_FLAGS"
author: windows-driver-content
description: Used to update the HW context state flags.
old-location: display\dxgk_updatehwcontextstate_flags.htm
old-project: display
ms.assetid: 23F0679A-05BB-4988-AF83-B6CC91C4CB79
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_UPDATEHWCONTEXTSTATE_FLAGS, DXGK_UPDATEHWCONTEXTSTATE_FLAGS structure [Display Devices], DXGK_UPDATEHWCONTEXTSTATE_FLAGS, d3dkmddi/DXGK_UPDATEHWCONTEXTSTATE_FLAGS, display.dxgk_updatehwcontextstate_flags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_UPDATEHWCONTEXTSTATE_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_UPDATEHWCONTEXTSTATE_FLAGS
---

# _DXGK_UPDATEHWCONTEXTSTATE_FLAGS structure


## -description


Used to update the HW context state flags.


## -syntax


````
typedef struct _DXGK_UPDATEHWCONTEXTSTATE_FLAGS {
  union {
    struct {
      UINT Suspended;
      UINT InterruptOnSwitchCompletion;
      UINT Reserved;
    };
    UINT Value;
  };
} DXGK_UPDATEHWCONTEXTSTATE_FLAGS;
````


## -struct-fields




### -field Suspended

Used to suspend the context. Otherwise, the context is runnable.


### -field InterruptOnSwitchCompletion

Used when the context state update is effective on the GPU.


### -field Reserved

This value is reserved for system use.


### -field Value

Used to operate over the rest of values.

