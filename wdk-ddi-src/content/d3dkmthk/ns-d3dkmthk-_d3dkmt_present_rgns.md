---
UID: NS:d3dkmthk._D3DKMT_PRESENT_RGNS
title: "_D3DKMT_PRESENT_RGNS"
author: windows-driver-content
description: Specifies dirty and move regions in a present operation.
old-location: display\d3dkmt_present_rgns.htm
old-project: display
ms.assetid: 90ae3382-0a2d-46cf-89e6-2148f0cbfc83
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_PRESENT_RGNS, D3DKMT_PRESENT_RGNS structure [Display Devices], _D3DKMT_PRESENT_RGNS, d3dkmthk/D3DKMT_PRESENT_RGNS, display.d3dkmt_present_rgns
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_PRESENT_RGNS
product: Windows
targetos: Windows
req.typenames: D3DKMT_PRESENT_RGNS
---

# _D3DKMT_PRESENT_RGNS structure


## -description


Specifies dirty and move regions in a present operation.


## -syntax


````
typedef struct _D3DKMT_PRESENT_RGNS {
  UINT                   DirtyRectCount;
  const RECT             *pDirtyRects;
  UINT                   MoveRectCount;
  const D3DKMT_MOVE_RECT *pMoveRects;
} D3DKMT_PRESENT_RGNS;
````


## -struct-fields




### -field DirtyRectCount

The number of dirty rectangles.


### -field pDirtyRects

A pointer to an array of dirty rectangles (<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>s).


### -field MoveRectCount

The number of move rectangles.


### -field pMoveRects

A pointer to an array of move rectangles (<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>s).


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 


