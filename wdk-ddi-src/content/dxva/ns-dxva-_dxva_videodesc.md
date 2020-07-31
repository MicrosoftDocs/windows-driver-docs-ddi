---
UID: NS:dxva._DXVA_VideoDesc
title: _DXVA_VideoDesc (dxva.h)
description: The DXVA_VideoDesc structure is sent by the renderer to the driver to specify a description of the video stream on which the deinterlacing or frame-rate conversion operation is to be performed.
old-location: display\dxva_videodesc.htm
tech.root: display
ms.assetid: 5623ed85-e78a-48f2-ab21-e6364da86b2a
ms.date: 05/10/2018
keywords: ["_DXVA_VideoDesc structure"]
ms.keywords: "*LPDXVA_VideoDesc, DXVA_VideoDesc, DXVA_VideoDesc structure [Display Devices], LPDXVA_VideoDesc, LPDXVA_VideoDesc structure pointer [Display Devices], _DXVA_VideoDesc, display.dxva_videodesc, dxva/DXVA_VideoDesc, dxva/LPDXVA_VideoDesc, dxvaref_1b9d87d3-06b4-4a61-9cb1-9752c55ef865.xml"
f1_keywords:
 - "dxva/DXVA_VideoDesc"
 - "DXVA_VideoDesc"
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
- DXVA_VideoDesc
targetos: Windows
req.typenames: DXVA_VideoDesc, *LPDXVA_VideoDesc
---

# _DXVA_VideoDesc structure


## -description


The DXVA_VideoDesc structure is sent by the renderer to the driver to specify a description of the video stream on which the deinterlacing or frame-rate conversion operation is to be performed.


## -struct-fields




### -field Size

Specifies the size of this structure, in bytes.


### -field SampleWidth

Specifies the width of the sample, in pixels.


### -field SampleHeight

Specifies the height of the sample, in pixels.


### -field SampleFormat

Specifies the format of the sample defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_sampleformat">DXVA_SampleFormat</a> structure.


### -field d3dFormat

Specifies the Direct3D surface format of the sample.


### -field InputSampleFreq

Specifies the frequency of incoming video defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_frequency">DXVA_Frequency</a> structure.


### -field OutputFrameFreq

Specifies the desired frame rate of output video as defined by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_frequency">DXVA_Frequency</a>.


## -remarks



For examples showing structure member values for deinterlacing or converting different types of content, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacecontainerdeviceclass-deinterlacequeryavailablemodes">DeinterlaceQueryAvailableModes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_frequency">DXVA_Frequency</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_sampleformat">DXVA_SampleFormat</a>
 

 

