---
UID: NE:dxva._DXVA_SampleFlags
title: "_DXVA_SampleFlags"
author: windows-driver-content
description: The DXVA_SampleFlags enumeration type contains a collection of flags that identify changes in the current sample frame from the previous sample frame.
old-location: display\dxva_sampleflags.htm
old-project: display
ms.assetid: 24f77f16-e043-4d58-87ef-6c834e61cb5d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA_SampleFlagsMask, dxva/DXVA_SampleFlagsMask, DXVA_SampleFlags, DXVA_SampleFlag_Palette_Changed, dxva/DXVA_SampleFlags, DXVA_SampleFlag_ColorData_Changed, dxvaref_b74a9819-950e-40cc-bf3c-eebb797862f7.xml, _DXVA_SampleFlags, dxva/DXVA_SampleFlag_DstRect_Changed, display.dxva_sampleflags, DXVA_SampleFlag_DstRect_Changed, DXVA_SampleFlag_SrcRect_Changed, DXVA_SampleFlags enumeration [Display Devices], dxva/DXVA_SampleFlag_Palette_Changed, dxva/DXVA_SampleFlag_SrcRect_Changed, dxva/DXVA_SampleFlag_ColorData_Changed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	dxva.h
apiname:
-	DXVA_SampleFlags
product: Windows
targetos: Windows
req.typenames: DXVA_SampleFlags
---

# _DXVA_SampleFlags enumeration


## -description


The DXVA_SampleFlags enumeration type contains a collection of flags that identify changes in the current sample frame from the previous sample frame.


## -syntax


````
typedef enum _DXVA_SampleFlags { 
  DXVA_SampleFlagsMask               = DXVABit(3)|DXVABit(2)|DXVABit(1)|DXVABit(0),
  DXVA_SampleFlag_Palette_Changed    = 0x0001,
  DXVA_SampleFlag_SrcRect_Changed    = 0x0002,
  DXVA_SampleFlag_DstRect_Changed    = 0x0004,
  DXVA_SampleFlag_ColorData_Changed  = 0x0008
} DXVA_SampleFlags;
````


## -enum-fields




### -field DXVA_SampleFlagsMask

Specifies the sample-flag mask, which consists of the first 4 bits of a DWORD. 


### -field DXVA_SampleFlag_Palette_Changed

Indicates that the palette of the sample frame changed. 


### -field DXVA_SampleFlag_SrcRect_Changed

Indicates that the source rectangle of the sample frame changed. 


### -field DXVA_SampleFlag_DstRect_Changed

Indicates that the destination rectangle of the sample frame changed. 


### -field DXVA_SampleFlag_ColorData_Changed

Indicates that the color data of the sample frame changed.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_videosample2.md">DXVA_VideoSample2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563927">DXVA_DeinterlaceBobDeviceClass::DeinterlaceBltEx</a>

<a href="..\dxva\ns-dxva-_dxva_deinterlacebltex.md">DXVA_DeinterlaceBltEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_SampleFlags enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

