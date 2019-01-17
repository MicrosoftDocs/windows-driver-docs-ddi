---
UID: NS:d3dkmddi._D3DKM_TRANSPARENTBLTFLAGS
title: "_D3DKM_TRANSPARENTBLTFLAGS"
description: The D3DKM_TRANSPARENTBLTFLAGS structure specifies the display adapter's ability to perform a hardware-accelerated bit-block transfer (bitblt) with transparency.
old-location: display\d3dkm_transparentbltflags.htm
ms.assetid: 8ac87e6e-bc24-45fe-b0c5-d253dd03da16
ms.date: 05/10/2018
ms.keywords: D3DKM_TRANSPARENTBLTFLAGS, D3DKM_TRANSPARENTBLTFLAGS structure [Display Devices], DmStructs_7190815e-5610-4c97-823f-8bdaae16c005.xml, _D3DKM_TRANSPARENTBLTFLAGS, d3dkmddi/D3DKM_TRANSPARENTBLTFLAGS, display.d3dkm_transparentbltflags
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	d3dkmddi.h
api_name:
-	D3DKM_TRANSPARENTBLTFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKM_TRANSPARENTBLTFLAGS
---

# _D3DKM_TRANSPARENTBLTFLAGS structure


## -description


The D3DKM_TRANSPARENTBLTFLAGS structure specifies the display adapter's ability to perform a hardware-accelerated bit-block transfer (bitblt) with transparency.


## -struct-fields




### -field HonorAlpha

[in] A UINT value that specifies in a hardware-accelerated transparent bit-block transfer whether the alpha channel should be used during comparison:

1 = The display adapter does not ignore the alpha channel when it compares the reference color with the source color.

0 = The display adapter ignores the alpha channel when it compares the reference color with the source color.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Value

[in] A member in the union that D3DKM_TRANSPARENTBLTFLAGS contains. This member can hold a 32-bit value that specifies the display adapter's ability to perform hardware-accelerated bit-block transfer with transparency.


## -remarks



For more information about how to use the members of this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561091">DXGK_GDIARG_TRANSPARENTBLT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561091">DXGK_GDIARG_TRANSPARENTBLT</a>
 

 

