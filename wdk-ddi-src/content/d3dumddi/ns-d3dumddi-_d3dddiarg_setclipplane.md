---
UID: NS:d3dumddi._D3DDDIARG_SETCLIPPLANE
title: "_D3DDDIARG_SETCLIPPLANE"
author: windows-driver-content
description: The D3DDDIARG_SETCLIPPLANE structure describes a clip plane.
old-location: display\d3dddiarg_setclipplane.htm
old-project: display
ms.assetid: 94e942a4-de66-47a3-89bf-fbec2a408775
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: UMDisplayDriver_param_Structs_3371265a-3cb5-4aee-b019-14ef454e9d6d.xml, display.d3dddiarg_setclipplane, D3DDDIARG_SETCLIPPLANE structure [Display Devices], _D3DDDIARG_SETCLIPPLANE, D3DDDIARG_SETCLIPPLANE, d3dumddi/D3DDDIARG_SETCLIPPLANE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_SETCLIPPLANE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETCLIPPLANE
---

# _D3DDDIARG_SETCLIPPLANE structure


## -description


The D3DDDIARG_SETCLIPPLANE structure describes a clip plane. 


## -syntax


````
typedef struct _D3DDDIARG_SETCLIPPLANE {
  UINT  Index;
  FLOAT Plane[4];
} D3DDDIARG_SETCLIPPLANE;
````


## -struct-fields




### -field Index

[in] The index of the clipping plane for which the plane equation coefficients are set.


### -field Plane

[in] A four-element array of the coefficients A, B, C, and D, in that order, in the general plane equation for the clipping plane. 


## -remarks



The general plane equation in standard form is A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> = 0. A point with homogeneous coordinates (<i>x</i>, <i>y</i>, <i>z</i>, <i>w</i>) is visible in the half-space of this plane if A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> &gt;= 0. Points that exist on or behind the clipping plane are clipped from the scene. That is, points for which A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> &lt; 0 are clipped.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setclipplane.md">SetClipPlane</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETCLIPPLANE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

