---
UID: NS:d3dumddi._DXVADDI_VIDEOPROCESSBLTFLAGS
title: _DXVADDI_VIDEOPROCESSBLTFLAGS
author: windows-driver-content
description: The DXVADDI_VIDEOPROCESSBLTFLAGS structure identifies changes in the current destination surface from the previous destination surface.
old-location: display\dxvaddi_videoprocessbltflags.htm
old-project: display
ms.assetid: 790a18fa-5481-432a-921b-6310a0ab78d7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVADDI_VIDEOPROCESSBLTFLAGS, DXVADDI_VIDEOPROCESSBLTFLAGS
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
req.alt-api: DXVADDI_VIDEOPROCESSBLTFLAGS
req.alt-loc: d3dumddi.h
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
req.typenames: DXVADDI_VIDEOPROCESSBLTFLAGS
---

# _DXVADDI_VIDEOPROCESSBLTFLAGS structure



## -description
The DXVADDI_VIDEOPROCESSBLTFLAGS structure identifies changes in the current destination surface from the previous destination surface.



## -syntax

````
typedef struct _DXVADDI_VIDEOPROCESSBLTFLAGS {
  union {
    struct {
      UINT BackgroundChanged  :1;
      UINT TargetRectChanged  :1;
      UINT ColorDataChanged  :1;
      UINT AlphaChanged  :1;
      UINT Reserved  :12;
      UINT DestData  :16;
    };
    UINT   Value;
  };
} DXVADDI_VIDEOPROCESSBLTFLAGS;
````


## -struct-fields

### -field BackgroundChanged

A UINT value that specifies whether the background color of the destination surface changed. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field TargetRectChanged

A UINT value that specifies whether the target rectangle of the destination surface changed. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field ColorDataChanged

A UINT value that specifies whether format information for the destination surface changed. Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field AlphaChanged

A UINT value that specifies whether the planar alpha value for the destination surface changed. Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the fifth through sixteenth bits (0x0000FFF0) of the 32-bit <b>Value</b> member to zeros.


### -field DestData

A UINT value that contains video processor sample destination data. Setting this member is equivalent to setting the seventeenth through thirty-second bits (0xFFFF0000) of the 32-bit <b>Value</b> member. The following bits can be set:

DXVADDI_DESTDATA_RFF (0x0001)

DXVADDI_DESTDATA_TFF (0x0002)

DXVADDI_DESTDATA_RFF_TFF_PRESENT (0x0004) 


### -field Value

A 32-bit value that identifies changes in the current destination surface from the previous destination surface.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOPROCESSBLTFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

