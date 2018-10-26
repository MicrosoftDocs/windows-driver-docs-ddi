---
UID: NS:d3dumddi._D3DDDI_OVERLAYINFOFLAGS
title: "_D3DDDI_OVERLAYINFOFLAGS"
author: windows-driver-content
description: The D3DDDI_OVERLAYINFOFLAGS structure identifies the type of overlay operation to perform.
old-location: display\d3dddi_overlayinfoflags.htm
tech.root: display
ms.assetid: ebf31c28-857b-4885-a910-16da5a011ce1
ms.date: 05/10/2018
ms.keywords: D3DDDI_OVERLAYINFOFLAGS, D3DDDI_OVERLAYINFOFLAGS structure [Display Devices], D3D_other_Structs_3c20db45-e3b5-4e0e-96a6-d2171dbf309a.xml, _D3DDDI_OVERLAYINFOFLAGS, d3dumddi/D3DDDI_OVERLAYINFOFLAGS, display.d3dddi_overlayinfoflags
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
-	D3DDDI_OVERLAYINFOFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_OVERLAYINFOFLAGS
---

# _D3DDDI_OVERLAYINFOFLAGS structure


## -description


The D3DDDI_OVERLAYINFOFLAGS structure identifies the type of overlay operation to perform.


## -struct-fields




### -field DstColorKey

A UINT value that specifies whether to perform destination color keying by using the value in the <b>DstColorKeyLow</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544621">D3DDDI_OVERLAYINFO</a> structure. That is, any pixel in the destination surface that matches the color key should be replaced with the corresponding pixel from the source resource, and all of the destination pixels that do not match the color key should not be replaced. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field DstColorKeyRange

A UINT value that specifies whether to perform destination color keying by using a range of values from the <b>DstColorKeyLow</b> and <b>DstColorKeyHigh</b> members of D3DDDI_OVERLAYINFO. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field SrcColorKey

A UINT value that specifies whether to perform source color keying by using the value in the <b>SrcColorKeyLow</b> member of D3DDDI_OVERLAYINFO. That is, any pixel in the source resource that matches the color key should not be copied to the destination surface, and all of the source pixels that do not match the color key should be copied. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field SrcColorKeyRange

A UINT value that specifies whether to perform source color keying by using a range of values from the <b>SrcColorKeyLow</b> and <b>SrcColorKeyHigh</b> members of D3DDDI_OVERLAYINFO.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Bob

A UINT value that specifies whether the overlay should deinterlace by using the <a href="https://msdn.microsoft.com/ef3220bd-841d-4187-bc86-11b999eae2bd">bob-style deinterlacing algorithm</a>.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field Interleaved

A UINT value that specifies whether the allocation that is being displayed contains both even and odd fields interleaved together.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field MirrorLeftRight

A UINT value that specifies whether the contents of the source resource are flipped horizontally along the center axis in the overlay to the destination surface. That is, contents on the left side of the source resource are copied to the right side of the destination surface, and vice versa.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field MirrorUpDown

A UINT value that specifies whether the contents of the source resource are flipped vertically along the center axis in the overlay to the destination surface. That is, contents on the top of the source resource are copied to the bottom of the destination surface, and vice versa.

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).


### -field Deinterlace

A UINT value that specifies whether the overlay should deinterlace the data in any manner the overlay requires.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).


### -field LimitedRGB

Supported in Windows 7 and later versions.

A UINT value that specifies whether the overlay is full range RGB or limited range RGB. Setting this member indicates limited range RGB. In limited range RGB, the RGB range is compressed such that 16:16:16 is black and 235:235:235 is white.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).


### -field YCbCrBT709

Supported in Windows 7 and later versions.

A UINT value that specifies whether the overlay is BT.601 or BT.709. Setting this member indicates BT.709, for high-definition TV (HDTV) and

is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).


### -field YCbCrxvYCC

Supported in Windows 7 and later versions.

A UINT value that specifies whether the overlay is conventional YCbCr or extended YCbCr (xvYCC). Setting this member indicates extended YCbCr (xvYCC) and is equivalent to setting the twelfth bit of the 32-bit <b>Value</b> member (0x00000800).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 20 bits (0xFFFFF000) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_OVERLAYINFOFLAGS that can hold one 32-bit value that identifies the type of overlay operation to perform.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544621">D3DDDI_OVERLAYINFO</a>
 

 

