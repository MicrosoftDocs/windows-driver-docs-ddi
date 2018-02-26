---
UID: NS:d3dkmthk._D3DKMT_SETVIDPNSOURCEOWNER2
title: "_D3DKMT_SETVIDPNSOURCEOWNER2"
author: windows-driver-content
description: Used to set the VidPN source owner.
old-location: display\d3dkmt-setvidpnsourceowner2.htm
old-project: display
ms.assetid: 6a6477db-23ad-42ad-b1cb-d81c7be4cf38
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 2, 3, C, D, D3DKMT_SETVIDPNSOURCEOWNER2, D3DKMT_SETVIDPNSOURCEOWNER2 structure [Display Devices], E, I, K, M, N, O, P, R, S, T, U, V, W, _, _D3DKMT_SETVIDPNSOURCEOWNER2, d3dkmthk/D3DKMT_SETVIDPNSOURCEOWNER2, display.d3dkmt-setvidpnsourceowner2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
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
-	d3dkmthk.h
apiname:
-	D3DKMT_SETVIDPNSOURCEOWNER2
product: Windows
targetos: Windows
req.typenames: D3DKMT_SETVIDPNSOURCEOWNER2
---

# _D3DKMT_SETVIDPNSOURCEOWNER2 structure


## -description


Used to set the VidPN source owner.


## -syntax


````
typedef struct _D3DKMT_SETVIDPNSOURCEOWNER2 {
  D3DKMT_SETVIDPNSOURCEOWNER1 Version1;
  HANDLE const*               *pVidPnSourceNtHandles;
} D3DKMT_SETVIDPNSOURCEOWNER2;
````


## -struct-fields




### -field Version1

The previous method used to set the VidPN source owner.


### -field pVidPnSourceNtHandles

A handle to the VidPN source owner handles.

