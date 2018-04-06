---
UID: NS:d3dumddi._D3DDDI_OVERLAYCOLORCONTROLSFLAGS
title: "_D3DDDI_OVERLAYCOLORCONTROLSFLAGS"
author: windows-driver-content
description: The D3DDDI_OVERLAYCOLORCONTROLSFLAGS structure identifies color-control settings that the overlay hardware supports.
old-location: display\d3dddi_overlaycolorcontrolsflags.htm
old-project: display
ms.assetid: 12907aee-7c67-48f9-bf0f-84428f2d4fa7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_OVERLAYCOLORCONTROLSFLAGS, D3DDDI_OVERLAYCOLORCONTROLSFLAGS structure [Display Devices], D3D_other_Structs_ada675f2-18ed-4597-bcc4-803d8598ae66.xml, _D3DDDI_OVERLAYCOLORCONTROLSFLAGS, d3dumddi/D3DDDI_OVERLAYCOLORCONTROLSFLAGS, display.d3dddi_overlaycolorcontrolsflags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDI_OVERLAYCOLORCONTROLSFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_OVERLAYCOLORCONTROLSFLAGS
---

# _D3DDDI_OVERLAYCOLORCONTROLSFLAGS structure


## -description


The D3DDDI_OVERLAYCOLORCONTROLSFLAGS structure identifies color-control settings that the overlay hardware supports.


## -struct-fields




### -field Brightness

A UINT value that specifies whether brightness adjustments to the overlay are enabled. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Contrast

A UINT value that specifies whether contrast adjustments to the overlay are enabled. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Hue

A UINT value that specifies whether hue adjustments to the overlay are enabled. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field Saturation

A UINT value that specifies whether saturation adjustments to the overlay are enabled.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Sharpness

A UINT value that specifies whether sharpness adjustments to the overlay are enabled.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field Gamma

A UINT value that specifies whether gamma adjustments to the overlay are enabled.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field ColorEnable

A UINT value that specifies whether color-enable adjustments to the overlay are enabled.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 25 bits (0xFFFFFF80) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that is contained in D3DDDI_OVERLAYCOLORCONTROLSFLAGS that can hold one 32-bit value that identifies color-control settings that the overlay hardware supports.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544612">D3DDDI_OVERLAYCOLORCONTROLS</a>
 

 

