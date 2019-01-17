---
UID: NS:dxva._DXVA_DeinterlaceBlt
title: "_DXVA_DeinterlaceBlt"
description: The DXVA_DeinterlaceBlt structure is sent by the VMR to the accelerator to specify the deinterlace or frame-rate conversion parameters for bit-block transfers.
old-location: display\dxva_deinterlaceblt.htm
tech.root: display
ms.assetid: 0512a825-9cec-4ca0-9686-df5b3d2b216b
ms.date: 05/10/2018
ms.keywords: DXVA_DeinterlaceBlt, DXVA_DeinterlaceBlt structure [Display Devices], _DXVA_DeinterlaceBlt, display.dxva_deinterlaceblt, dxva/DXVA_DeinterlaceBlt, dxvaref_69a3b788-495c-42a0-acae-8d8242d963c6.xml
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	dxva.h
api_name:
-	DXVA_DeinterlaceBlt
product:
- Windows
targetos: Windows
req.typenames: DXVA_DeinterlaceBlt
---

# _DXVA_DeinterlaceBlt structure


## -description


The DXVA_DeinterlaceBlt structure is sent by the VMR to the accelerator to specify the deinterlace or frame-rate conversion parameters for bit-block transfers.


## -struct-fields




### -field Size

Specifies the size of this structure in bytes.


### -field Reserved


### -field rtTarget

Identifies the location of the output frame within the sequence of input frames. If only deinterlacing is performed, the target time should coincide with either the starting display time of a reference sample, as defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564085">DXVA_VideoSample</a> structure, or the midpoint between the starting display time and the ending display time. For more information, see Remarks.

If a frame rate conversion is requested, the <b>rtTarget</b> time can be different from any of the <b>rtStart</b> times of the reference samples.


### -field DstRect

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the upper left and lower right points of a rectangle on the destination surface. These points define the area in which the bit-block transfer should occur and its position on the destination surface.


### -field SrcRect

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the upper left and lower right points of a rectangle on the source surface. These points define the area of the source data for the bit-block transfer and its position on the source surface.


### -field NumSourceSurfaces

Specifies the number of valid surfaces passed in the <b>Source</b> array.


### -field Alpha

Specifies the transparency of the output image as it is written to the destination surface. A value of  0.0F indicates transparent. A value of 1.0F indicates opaque.


### -field Source

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564085">DXVA_VideoSample</a> structures that specify the reference input samples needed for this deinterlacing or frame-rate conversion operation.


## -remarks



When creating a single frame from one field in a sample, as defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564085">DXVA_VideoSample</a> structure, <b>rtTarget</b> should be the starting display time for that field. If you have two fields in one sample and want to deinterlace both, <a href="https://msdn.microsoft.com/0aa68d0c-8c2b-41fe-9e46-a41b157fbd98">DeinterlaceBlt</a> will be called twice. The first time <i>DeinterlaceBlt</i> is called, <b>rtTarget</b> will be the starting display time. The second time <i>DeinterlaceBlt</i> is called, <b>rtTarget</b> will be the midpoint between the starting display time and the ending display time. In other words, for the first call, <b>rtTarget</b> = <b>rtStart</b>. For the second call, <b>rtTarget</b> = (<b>rtStart</b> + <b>rtEnd</b>) / 2.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563939">DXVA_DeinterlaceCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564085">DXVA_VideoSample</a>



<a href="https://msdn.microsoft.com/0aa68d0c-8c2b-41fe-9e46-a41b157fbd98">DeinterlaceBlt</a>
 

 

