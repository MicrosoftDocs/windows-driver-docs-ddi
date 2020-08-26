---
UID: NS:dxva._DXVA_DeinterlaceBltEx32
title: _DXVA_DeinterlaceBltEx32 (dxva.h)
description: The DXVA_DeinterlaceBltEx structure describes parameters for deinterlace or frame-rate conversion, for combining the deinterlaced or frame-rate converted video with any supplied video substreams, and for writing the combined output to a destination surface. It is used for forwarding 32-bit DXVA_DeinterlaceBltEx calls on 64-bit drivers.
old-location: display\dxva_deinterlacebltex32.htm
tech.root: display
ms.assetid: ae88acca-5d29-4cca-acae-613632d565d8
ms.date: 05/10/2018
keywords: ["DXVA_DeinterlaceBltEx32 structure"]
ms.keywords: DXVA_DeinterlaceBltEx32, DXVA_DeinterlaceBltEx32 structure [Display Devices], _DXVA_DeinterlaceBltEx32, display.dxva_deinterlacebltex32, dxva/DXVA_DeinterlaceBltEx32, dxvaref_93b5f3fe-0474-4efe-8d8f-b57e5c3f267d.xml
f1_keywords:
 - "dxva/DXVA_DeinterlaceBltEx32"
 - "DXVA_DeinterlaceBltEx32"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.Only compiles for a 64-bit version of the operating system.
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
- DXVA_DeinterlaceBltEx32
targetos: Windows
req.typenames: DXVA_DeinterlaceBltEx32
---

# _DXVA_DeinterlaceBltEx32 structure


## -description


The DXVA_DeinterlaceBltEx structure describes parameters for deinterlace or frame-rate conversion, for combining the deinterlaced or frame-rate converted video with any supplied video substreams, and for writing the combined output to a destination surface. It is used for forwarding  32-bit <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacebltex">DXVA_DeinterlaceBltEx</a> calls on 64-bit drivers. 


## -struct-fields




### -field Size

Specifies the size of the structure, in bytes.


### -field BackgroundColor

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_ayuvsample2">DXVA_AYUVsample2</a> structure that identifies background color and opacity level. For Windows Server 2003 with SP1 and Windows XP with SP2, the opacity level is not used and should be ignored by the driver.


### -field rcTarget

Specifies a pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure that describes the location within the destination surface to which the output image is written. Note that the output image is restricted to the pixels within the <b>rcTarget</b> rectangle--that is, every pixel within this rectangle must be written to; pixels outside this rectangle must not be modified. 


### -field rtTarget

Identifies the location of the output frame within the sequence of input frames. If only deinterlacing is performed, the target time should coincide with either the starting display time of a sample, as defined in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videosample32">DXVA_VideoSample32</a> structure, or the midpoint between the starting display time and the ending display time. For more information, see Remarks.

If a frame-rate conversion is requested, the <b>rtTarget</b> time can be different from any of the <b>rtStart</b> times of the samples.


### -field NumSourceSurfaces

Specifies the number of valid surfaces passed in the <b>Source</b> array.


### -field Alpha

Specifies the planar-transparency value of the output image as it is written to the destination surface. For Windows Server 2003 with SP1 and Windows XP with SP2, this value is always 1.0F, which indicates that the overall image is opaque and that no alpha blending on the overall image is required.


### -field Source

Specifies an array of DXVA_VideoSample32 structures that describe the input samples that are required for the deinterlacing, frame-rate conversion, and substream-compositing operations. For information about how input samples are arranged in this array, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/input-buffer-order">Input Buffer Order</a>.


### -field DestinationFormat

Specifies format information for the destination surface. For Windows Server 2003 with SP1 and Windows XP with SP2, this member is set to 0.


### -field DestinationFlags

Specifies a collection of flags that indicate changes in the current destination surface from the previous destination surface. This member is a bitwise-OR of one or more of the flags in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_destinationflags">DXVA_DestinationFlags</a> enumeration type.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacecaps">DXVA_DeinterlaceCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_destinationflags">DXVA_DestinationFlags</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videosample32">DXVA_VideoSample32</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a>
 

 

