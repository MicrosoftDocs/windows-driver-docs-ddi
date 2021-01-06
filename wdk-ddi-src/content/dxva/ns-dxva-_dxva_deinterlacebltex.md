---
UID: NS:dxva._DXVA_DeinterlaceBltEx
title: _DXVA_DeinterlaceBltEx (dxva.h)
description: The DXVA_DeinterlaceBltEx structure describes parameters for deinterlace or frame-rate conversion, for combining the deinterlaced or frame-rate-converted video with any supplied video substreams, and for writing the combined output to a destination surface.
old-location: display\dxva_deinterlacebltex.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVA_DeinterlaceBltEx structure"]
ms.keywords: DXVA_DeinterlaceBltEx, DXVA_DeinterlaceBltEx structure [Display Devices], _DXVA_DeinterlaceBltEx, display.dxva_deinterlacebltex, dxva/DXVA_DeinterlaceBltEx, dxvaref_4340e54b-79b9-44a1-9d29-37f6aae9fe94.xml
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
targetos: Windows
req.typenames: DXVA_DeinterlaceBltEx
f1_keywords:
 - _DXVA_DeinterlaceBltEx
 - dxva/_DXVA_DeinterlaceBltEx
 - DXVA_DeinterlaceBltEx
 - dxva/DXVA_DeinterlaceBltEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - DXVA_DeinterlaceBltEx
---

# _DXVA_DeinterlaceBltEx structure


## -description

The DXVA_DeinterlaceBltEx structure describes parameters for deinterlace or frame-rate conversion, for combining the deinterlaced or frame-rate-converted video with any supplied video substreams, and for writing the combined output to a destination surface.

## -struct-fields

### -field Size

Specifies the size of the structure, in bytes.

### -field BackgroundColor

Specifies a <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_ayuvsample2">DXVA_AYUVsample2</a> structure that identifies background color and opacity level. For Windows Server 2003 with SP1 and Windows XP with SP2, the opacity level is not used and should be ignored by the driver.

### -field rcTarget

Specifies a pointer to a <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure that describes the location within the destination surface to which the output image is written. Note that the output image is restricted to the pixels within the <b>rcTarget</b> rectangle--that is, every pixel within this rectangle must be written to; pixels outside this rectangle must not be modified.

### -field rtTarget

Identifies the location of the output frame within the sequence of input frames. If only deinterlacing is performed, the target time should coincide with either the starting display time of a sample, as defined in the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videosample2">DXVA_VideoSample2</a> structure, or the midpoint between the starting display time and the ending display time. For more information, see Remarks.

If a frame-rate conversion is requested, the <b>rtTarget</b> time can be different from any of the <b>rtStart</b> times of the samples.

### -field NumSourceSurfaces

Specifies the number of valid surfaces passed in the <b>Source</b> array.

### -field Alpha

Specifies the planar-transparency value of the output image as it is written to the destination surface. For Windows Server 2003 with SP1 and Windows XP with SP2, this value is always 1.0F, which indicates that the overall image is opaque and that no alpha blending on the overall image is required.

### -field Source

Specifies an array of DXVA_VideoSample2 structures that describe the input samples that are required for the deinterlacing, frame-rate conversion, and substream-compositing operations. For information about how input samples are arranged in this array, see <a href="/windows-hardware/drivers/display/input-buffer-order">Input Buffer Order</a>.

### -field DestinationFormat

Specifies format information for the destination surface. For Windows Server 2003 with SP1 and Windows XP with SP2, this member is set to 0.

### -field DestinationFlags

Specifies a collection of flags that indicate changes in the current destination surface from the previous destination surface. This member is a bitwise-OR of one or more of the flags in the <a href="/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_destinationflags">DXVA_DestinationFlags</a> enumeration type.

## -remarks

The render sends the DXVA_DeinterlaceBltEx structure to the accelerator to specify the deinterlace or frame-rate conversion parameters for bit-block transfers. 

When a single frame is being created from one field in a sample, as defined in the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videosample2">DXVA_VideoSample2</a> structure, <b>rtTarget</b> should be the starting display time for that field. If you have two fields in one sample and want to deinterlace both, <a href="/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> will be called twice. The first time <i>DeinterlaceBltEx</i> is called, <b>rtTarget</b> will be the starting display time. The second time <i>DeinterlaceBltEx</i> is called, <b>rtTarget</b> will be the midpoint between the starting display time and the ending display time. In other words, for the first call, <b>rtTarget</b> = <b>rtStart</b>. For the second call, <b>rtTarget</b> = (<b>rtStart</b> + <b>rtEnd</b>) / 2.

## -see-also

<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacecaps">DXVA_DeinterlaceCaps</a>



<a href="/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_destinationflags">DXVA_DestinationFlags</a>



<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videosample2">DXVA_VideoSample2</a>



<a href="/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a>
