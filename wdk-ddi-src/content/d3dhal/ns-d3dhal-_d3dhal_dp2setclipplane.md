---
UID: NS:d3dhal._D3DHAL_DP2SETCLIPPLANE
title: "_D3DHAL_DP2SETCLIPPLANE"
author: windows-driver-content
description: The D3DHAL_SETCLIPPLANE structure allows user defined clip planes to be used in world space.
old-location: display\d3dhal_dp2setclipplane.htm
old-project: display
ms.assetid: 84459f39-42cb-4877-b569-17c51ee2d6e4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: LPD3DHAL_DP2SETCLIPPLANE, D3DHAL_DP2SETCLIPPLANE, display.d3dhal_dp2setclipplane, _D3DHAL_DP2SETCLIPPLANE, D3DHAL_DP2SETCLIPPLANE structure [Display Devices], d3dhal/D3DHAL_DP2SETCLIPPLANE, d3dstrct_91eb9840-4f5f-42c2-84e7-d2461d484bbf.xml, LPD3DHAL_DP2SETCLIPPLANE structure pointer [Display Devices], d3dhal/LPD3DHAL_DP2SETCLIPPLANE, *LPD3DHAL_DP2SETCLIPPLANE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
-	d3dhal.h
apiname:
-	D3DHAL_DP2SETCLIPPLANE
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETCLIPPLANE
---

# _D3DHAL_DP2SETCLIPPLANE structure


## -description


The D3DHAL_SETCLIPPLANE structure allows user defined clip planes to be used in world space.


## -syntax


````
typedef struct _D3DHAL_DP2SETCLIPPLANE {
  DWORD    dwIndex;
  D3DVALUE plane[4];
} D3DHAL_DP2SETCLIPPLANE, *LPD3DHAL_DP2SETCLIPPLANE;
````


## -struct-fields




### -field dwIndex

Specifies the index of the clipping plane for which the plane equation coefficients will be set.


### -field plane

Specifies a four-element array of the coefficients A, B, C, and D, in that order, in the general plane equation for the clipping plane. 


## -remarks



The general plane equation in standard form is A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i>  = 0. A point with homogeneous coordinates (<i>x</i>, <i>y</i>, <i>z</i>, <i>w</i>) is visible in the half-space of this plane if A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i>  &gt;= 0. Points that exist on or behind the clipping plane are clipped from the scene. That is, points for which Ax + By + Cz + Dw &lt;= 0 are clipped.



