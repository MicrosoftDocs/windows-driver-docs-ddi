---
UID: NS:d3dumddi._DXVADDI_QUERYFILTERPROPERTYRANGEINPUT
title: "_DXVADDI_QUERYFILTERPROPERTYRANGEINPUT"
description: The DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure describes a filter setting on a video stream that range information is requested for.
old-location: display\dxvaddi_queryfilterpropertyrangeinput.htm
tech.root: display
ms.assetid: d073d326-6cc6-4216-b312-809d707aef3b
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_28a2aed9-57a1-4bd6-b8dc-c09bb9e821b0.xml, DXVADDI_QUERYFILTERPROPERTYRANGEINPUT, DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure [Display Devices], _DXVADDI_QUERYFILTERPROPERTYRANGEINPUT, d3dumddi/DXVADDI_QUERYFILTERPROPERTYRANGEINPUT, display.dxvaddi_queryfilterpropertyrangeinput
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVADDI_QUERYFILTERPROPERTYRANGEINPUT
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_QUERYFILTERPROPERTYRANGEINPUT
---

# _DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure


## -description


The DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure describes a filter setting on a video stream that range information is requested for.


## -struct-fields




### -field pVideoProcGuid

[in] A pointer to a GUID that represents the video processing device type. 


### -field VideoDesc

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a> structure that describes the video stream.


### -field RenderTargetFormat

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.


### -field FilterSetting

[in] A filter setting that range information is requested for. This member can be one of the following settings:

<ul>
<li>
DXVADDI_NOISEFILTER_LUMALEVEL

</li>
<li>
DXVADDI_NOISEFILTER_LUMATHREASHOLD

</li>
<li>
DXVADDI_NOISEFILTER_LUMARADIUS

</li>
<li>
DXVADDI_NOISEFILTER_CHROMALEVEL

</li>
<li>
DXVADDI_NOISEFILTER_CHROMATHREASHOLD

</li>
<li>
DXVADDI_NOISEFILTER_CHROMARADIUS

</li>
<li>
DXVADDI_DETAILFILTER_LUMALEVEL

</li>
<li>
DXVADDI_DETAILFILTER_LUMATHREASHOLD

</li>
<li>
DXVADDI_DETAILFILTER_LUMARADIUS

</li>
<li>
DXVADDI_DETAILFILTER_CHROMALEVEL

</li>
<li>
DXVADDI_DETAILFILTER_CHROMATHREASHOLD

</li>
<li>
DXVADDI_DETAILFILTER_CHROMARADIUS

</li>
</ul>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562939">DXVADDI_VALUERANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

