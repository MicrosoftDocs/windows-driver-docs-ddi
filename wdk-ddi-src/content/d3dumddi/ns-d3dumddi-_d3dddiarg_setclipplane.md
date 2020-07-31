---
UID: NS:d3dumddi._D3DDDIARG_SETCLIPPLANE
title: _D3DDDIARG_SETCLIPPLANE (d3dumddi.h)
description: The D3DDDIARG_SETCLIPPLANE structure describes a clip plane.
old-location: display\d3dddiarg_setclipplane.htm
tech.root: display
ms.assetid: 94e942a4-de66-47a3-89bf-fbec2a408775
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_SETCLIPPLANE structure"]
ms.keywords: D3DDDIARG_SETCLIPPLANE, D3DDDIARG_SETCLIPPLANE structure [Display Devices], UMDisplayDriver_param_Structs_3371265a-3cb5-4aee-b019-14ef454e9d6d.xml, _D3DDDIARG_SETCLIPPLANE, d3dumddi/D3DDDIARG_SETCLIPPLANE, display.d3dddiarg_setclipplane
f1_keywords:
 - "d3dumddi/D3DDDIARG_SETCLIPPLANE"
 - "D3DDDIARG_SETCLIPPLANE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_SETCLIPPLANE
targetos: Windows
req.typenames: D3DDDIARG_SETCLIPPLANE
---

# _D3DDDIARG_SETCLIPPLANE structure


## -description


The D3DDDIARG_SETCLIPPLANE structure describes a clip plane. 


## -struct-fields




### -field Index

[in] The index of the clipping plane for which the plane equation coefficients are set.


### -field Plane

[in] A four-element array of the coefficients A, B, C, and D, in that order, in the general plane equation for the clipping plane. 


## -remarks



The general plane equation in standard form is A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> = 0. A point with homogeneous coordinates (<i>x</i>, <i>y</i>, <i>z</i>, <i>w</i>) is visible in the half-space of this plane if A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> >= 0. Points that exist on or behind the clipping plane are clipped from the scene. That is, points for which A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> < 0 are clipped.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setclipplane">SetClipPlane</a>
 

 

