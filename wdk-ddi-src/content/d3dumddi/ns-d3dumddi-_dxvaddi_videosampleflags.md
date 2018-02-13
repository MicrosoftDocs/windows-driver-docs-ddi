---
UID: NS:d3dumddi._DXVADDI_VIDEOSAMPLEFLAGS
title: "_DXVADDI_VIDEOSAMPLEFLAGS"
author: windows-driver-content
description: The DXVADDI_VIDEOSAMPLEFLAGS structure identifies changes in the current sample frame from the previous sample frame.
old-location: display\dxvaddi_videosampleflags.htm
old-project: display
ms.assetid: 1dca2b12-0542-43a9-abff-203ea34cff90
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/DXVADDI_VIDEOSAMPLEFLAGS, _DXVADDI_VIDEOSAMPLEFLAGS, DXVA2_Structs_8e0fce9f-8473-4bbc-9403-fb8755090a7d.xml, DXVADDI_VIDEOSAMPLEFLAGS structure [Display Devices], display.dxvaddi_videosampleflags, DXVADDI_VIDEOSAMPLEFLAGS
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
-	DXVADDI_VIDEOSAMPLEFLAGS
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOSAMPLEFLAGS
---

# _DXVADDI_VIDEOSAMPLEFLAGS structure


## -description


The DXVADDI_VIDEOSAMPLEFLAGS structure identifies changes in the current sample frame from the previous sample frame.


## -syntax


````
typedef struct _DXVADDI_VIDEOSAMPLEFLAGS {
  union {
    struct {
      UINT PaletteChanged  :1;
      UINT SrcRectChanged  :1;
      UINT DstRectChanged  :1;
      UINT ColorDataChanged  :1;
      UINT PlanarAlphaChanged  :1;
      UINT Reserved  :11;
      UINT SampleData  :16;
    };
    UINT   Value;
  };
} DXVADDI_VIDEOSAMPLEFLAGS;
````


## -struct-fields




### -field PaletteChanged

A UINT value that specifies whether the palette of the sample frame changed. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field SrcRectChanged

A UINT value that specifies whether the source rectangle of the sample frame changed. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field DstRectChanged

A UINT value that specifies whether the destination rectangle of the sample frame changed. Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field ColorDataChanged

A UINT value that specifies whether the color data of the sample frame changed. Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field PlanarAlphaChanged

A UINT value that specifies whether the alpha (transparency) data of the sample frame changed. Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the sixth through sixteenth bits (0x0000FFE0) of the 32-bit <b>Value</b> member to zeros.


### -field SampleData

A UINT value that contains video sample data. Setting this member is equivalent to setting the seventeenth through thirty-second bits (0xFFFF0000) of the 32-bit <b>Value</b> member. The following bits can be set:

DXVADDI_SAMPLEDATA_RFF (0x0001)

DXVADDI_SAMPLEDATA_TFF (0x0002)

DXVADDI_SAMPLEDATA_RFF_TFF_PRESENT (0x0004) 


### -field Value

A member in the union that is contained in DXVADDI_VIDEOSAMPLEFLAGS that can hold one 32-bit value that identifies changes in the current sample frame from the previous sample frame.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videosample.md">DXVADDI_VIDEOSAMPLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOSAMPLEFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

