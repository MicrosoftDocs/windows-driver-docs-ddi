---
UID: NS:d3dkmdt._D3DKMT_MOVE_RECT
title: "_D3DKMT_MOVE_RECT"
author: windows-driver-content
description: Provides information on a screen-to-screen move and a dirty rectangle copy operation.
old-location: display\d3dkmt_move_rect.htm
old-project: display
ms.assetid: 2d9e0a8e-9485-427d-bdd0-2d89dec76a77
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_MOVE_RECT, D3DKMT_MOVE_RECT structure [Display Devices], _D3DKMT_MOVE_RECT, d3dkmdt/D3DKMT_MOVE_RECT, display.d3dkmt_move_rect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: 
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
-	D3dkmdt.h
api_name:
-	D3DKMT_MOVE_RECT
product: Windows
targetos: Windows
req.typenames: D3DKMT_MOVE_RECT
---

# _D3DKMT_MOVE_RECT structure


## -description


Provides information on a screen-to-screen move and a dirty rectangle copy operation.


## -syntax


````
typedef struct _D3DKMT_MOVE_RECT {
  POINT SourcePoint;
  RECT  DestRect;
} D3DKMT_MOVE_RECT;
````


## -struct-fields




### -field SourcePoint

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a> structure that describes the source (<i>x, y</i>) point where the source rectangle is copied from.


### -field DestRect

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that contains the destination rectangle where the dirty rectangle is copied to.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 


