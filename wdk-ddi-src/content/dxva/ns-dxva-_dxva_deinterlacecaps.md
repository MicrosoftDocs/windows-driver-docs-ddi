---
UID: NS:dxva._DXVA_DeinterlaceCaps
title: _DXVA_DeinterlaceCaps (dxva.h)
description: The DXVA_DeinterlaceCaps structure describes the driver capabilities for a deinterlace mode.
old-location: display\dxva_deinterlacecaps.htm
tech.root: display
ms.assetid: be503505-fb20-4a8d-b395-7e807cde9fb6
ms.date: 05/10/2018
keywords: ["DXVA_DeinterlaceCaps structure"]
ms.keywords: "*LPDXVA_DeinterlaceCaps, DXVA_DeinterlaceCaps, DXVA_DeinterlaceCaps structure [Display Devices], LPDXVA_DeinterlaceCaps, LPDXVA_DeinterlaceCaps structure pointer [Display Devices], _DXVA_DeinterlaceCaps, display.dxva_deinterlacecaps, dxva/DXVA_DeinterlaceCaps, dxva/LPDXVA_DeinterlaceCaps, dxvaref_daa1a58d-aec2-4370-9baa-7a3b8cbcacf8.xml"
f1_keywords:
 - "dxva/DXVA_DeinterlaceCaps"
 - "DXVA_DeinterlaceCaps"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_DeinterlaceCaps
targetos: Windows
req.typenames: DXVA_DeinterlaceCaps, *LPDXVA_DeinterlaceCaps
---

# _DXVA_DeinterlaceCaps structure


## -description


The DXVA_DeinterlaceCaps structure describes the driver capabilities for a deinterlace mode.


## -struct-fields




### -field Size

Indicates the size of this structure.


### -field NumPreviousOutputFrames

Indicates the number of required frames previously output by the deinterlace algorithm. This member is used by recursive deinterlace algorithms.


### -field InputPool

Indicates the memory pool from which the interlaced source surfaces should be allocated. For more information, see the D3DPOOL enumeration type in the Microsoft Window SDK documentation. 


### -field NumForwardRefSamples

Indicates the required number of forward reference samples for the defined deinterlace mode. These samples will be in future fields. This value is zero for bob and line blending, and can be several values for adaptive deinterlacing and frame-rate conversion.


### -field NumBackwardRefSamples

Indicates the required backward reference samples for the defined deinterlace mode. The samples are in past fields. This value is zero for bob, 1 for line blending, and can be several values for adaptive deinterlacing and frame-rate conversion.


### -field d3dOutputFormat

Indicates the Direct3D surface format of the output frames. Usually a deinterlace algorithm outputs frames in a surface format that matches the input sample format. This member ensures that the VMR or other video renderer will be able to supply the correct output frame surfaces to the deinterlace hardware.

Note that if the <b>DXVA_Deinterlace_YUV2RGB</b> enumerator is returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videoprocesscaps">DXVA_VideoProcessCaps</a> enumeration, the VMR will assume that valid output formats are specified by this member, in addition to a D3DFMT_X8R8G8B8 format.


### -field VideoProcessingCaps

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videoprocesscaps">DXVA_VideoProcessCaps</a> enumeration indicating the operation that can be performed concurrently with the requested deinterlace. 


### -field DeinterlaceTechnology

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_deinterlacetech">DXVA_DeinterlaceTech</a> enumeration indicating the deinterlacing technology used by this deinterlacing device.


## -remarks



The driver receives the DXVA_DeinterlaceCaps structure with the <b>Size</b> member assigned, assigns values to the remaining members, and returns DXVA_DeinterlaceCaps to the renderer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_deinterlacetech">DXVA_DeinterlaceTech</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videoprocesscaps">DXVA_VideoProcessCaps</a>
 

 

