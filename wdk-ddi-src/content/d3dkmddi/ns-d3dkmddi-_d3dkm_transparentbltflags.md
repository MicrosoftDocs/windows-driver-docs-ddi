---
UID: NS:d3dkmddi._D3DKM_TRANSPARENTBLTFLAGS
title: "_D3DKM_TRANSPARENTBLTFLAGS"
author: windows-driver-content
description: The D3DKM_TRANSPARENTBLTFLAGS structure specifies the display adapter's ability to perform a hardware-accelerated bit-block transfer (bitblt) with transparency.
old-location: display\d3dkm_transparentbltflags.htm
old-project: display
ms.assetid: 8ac87e6e-bc24-45fe-b0c5-d253dd03da16
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/D3DKM_TRANSPARENTBLTFLAGS, D3DKM_TRANSPARENTBLTFLAGS structure [Display Devices], DmStructs_7190815e-5610-4c97-823f-8bdaae16c005.xml, D3DKM_TRANSPARENTBLTFLAGS, display.d3dkm_transparentbltflags, _D3DKM_TRANSPARENTBLTFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	D3DKM_TRANSPARENTBLTFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKM_TRANSPARENTBLTFLAGS
---

# _D3DKM_TRANSPARENTBLTFLAGS structure


## -description


The D3DKM_TRANSPARENTBLTFLAGS structure specifies the display adapter's ability to perform a hardware-accelerated bit-block transfer (bitblt) with transparency.


## -syntax


````
typedef struct _D3DKM_TRANSPARENTBLTFLAGS {
  union {
    struct {
      UINT HonorAlpha  :1;
    };
    UINT   Value;
  };
} D3DKM_TRANSPARENTBLTFLAGS;
````


## -struct-fields




### -field HonorAlpha

[in] A UINT value that specifies in a hardware-accelerated transparent bit-block transfer whether the alpha channel should be used during comparison:

1 = The display adapter does not ignore the alpha channel when it compares the reference color with the source color.

0 = The display adapter ignores the alpha channel when it compares the reference color with the source color.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Value

[in] A member in the union that D3DKM_TRANSPARENTBLTFLAGS contains. This member can hold a 32-bit value that specifies the display adapter's ability to perform hardware-accelerated bit-block transfer with transparency.


## -remarks


For more information about how to use the members of this structure, see <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md">DXGK_GDIARG_TRANSPARENTBLT</a>.



## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md">DXGK_GDIARG_TRANSPARENTBLT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKM_TRANSPARENTBLTFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

