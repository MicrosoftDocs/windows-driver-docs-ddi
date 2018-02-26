---
UID: NS:d3dumddi._D3DDDICB_CREATEHWCONTEXT
title: "_D3DDDICB_CREATEHWCONTEXT"
author: windows-driver-content
description: A structure that gives information for creating a hardware context.
old-location: display\d3dddicb_createhwcontext.htm
old-project: display
ms.assetid: DA1C3976-0261-4FF1-8E49-EDF93D7BED22
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, B, C, D, D3DDDICB_CREATEHWCONTEXT, D3DDDICB_CREATEHWCONTEXT structure [Display Devices], E, H, I, N, O, R, T, W, X, _, _D3DDDICB_CREATEHWCONTEXT, d3dumddi/D3DDDICB_CREATEHWCONTEXT, display.d3dddicb_createhwcontext"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDICB_CREATEHWCONTEXT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_CREATEHWCONTEXT
---

# _D3DDDICB_CREATEHWCONTEXT structure


## -description


A structure that gives information for creating a hardware context.


## -syntax


````
typedef struct _D3DDDICB_CREATEHWCONTEXT {
  UINT                         NodeOrdinal;
  UINT                         EngineAffinity;
  3DDDI_CREATEHWCONTEXTFLAGS   Flags;
  UINT                         PrivateDriverDataSize;
  VOID                         *pPrivateDriverData;
  HANDLE                       hHwContext;
} D3DDDICB_CREATEHWCONTEXT;
````


## -struct-fields




### -field NodeOrdinal

Specifies the node ordinal this context is targeted to.


### -field EngineAffinity

Specifies the engine affinity within the node.


### -field Flags

Hardware context creation flags.


### -field PrivateDriverDataSize

Size of private driver data.


### -field pPrivateDriverData

Pointer to private driver data.


### -field hHwContext

Handle to the created context.

