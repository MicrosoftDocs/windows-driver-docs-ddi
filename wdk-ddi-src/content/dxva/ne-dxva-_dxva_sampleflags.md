---
UID: NE:dxva._DXVA_SampleFlags
title: _DXVA_SampleFlags (dxva.h)
description: The DXVA_SampleFlags enumeration type contains a collection of flags that identify changes in the current sample frame from the previous sample frame.
old-location: display\dxva_sampleflags.htm
tech.root: display
ms.assetid: 24f77f16-e043-4d58-87ef-6c834e61cb5d
ms.date: 05/10/2018
keywords: ["_DXVA_SampleFlags enumeration"]
ms.keywords: DXVA_SampleFlag_ColorData_Changed, DXVA_SampleFlag_DstRect_Changed, DXVA_SampleFlag_Palette_Changed, DXVA_SampleFlag_SrcRect_Changed, DXVA_SampleFlags, DXVA_SampleFlags enumeration [Display Devices], DXVA_SampleFlagsMask, _DXVA_SampleFlags, display.dxva_sampleflags, dxva/DXVA_SampleFlag_ColorData_Changed, dxva/DXVA_SampleFlag_DstRect_Changed, dxva/DXVA_SampleFlag_Palette_Changed, dxva/DXVA_SampleFlag_SrcRect_Changed, dxva/DXVA_SampleFlags, dxva/DXVA_SampleFlagsMask, dxvaref_b74a9819-950e-40cc-bf3c-eebb797862f7.xml
f1_keywords:
 - "dxva/DXVA_SampleFlags"
 - "DXVA_SampleFlags"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_SampleFlags
product:
- Windows
targetos: Windows
req.typenames: DXVA_SampleFlags
---

# _DXVA_SampleFlags enumeration


## -description


The DXVA_SampleFlags enumeration type contains a collection of flags that identify changes in the current sample frame from the previous sample frame.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacebltex">DXVA_DeinterlaceBltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DXVA_DeinterlaceBobDeviceClass::DeinterlaceBltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videosample2">DXVA_VideoSample2</a>
 

 

