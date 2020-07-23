---
UID: NS:d3dumddi._DXVAHDDDI_SURFACE
title: _DXVAHDDDI_SURFACE (d3dumddi.h)
description: The DXVAHDDDI_SURFACE structure describes a surface.
old-location: display\dxvahdddi_surface.htm
tech.root: display
ms.assetid: a0bfc9bf-777e-4da4-9414-856ec650375d
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_SURFACE structure"]
ms.keywords: DXVA2_Structs_8032b044-07e9-4bb7-9367-1c3283bbf145.xml, DXVAHDDDI_SURFACE, DXVAHDDDI_SURFACE structure [Display Devices], _DXVAHDDDI_SURFACE, d3dumddi/DXVAHDDDI_SURFACE, display.dxvahdddi_surface
f1_keywords:
 - "d3dumddi/DXVAHDDDI_SURFACE"
 - "DXVAHDDDI_SURFACE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DXVAHDDDI_SURFACE
targetos: Windows
req.typenames: DXVAHDDDI_SURFACE
---

# _DXVAHDDDI_SURFACE structure


## -description


The DXVAHDDDI_SURFACE structure describes a surface. 


## -struct-fields




### -field hResource

[in] A handle to the resource that contains the surface. 


### -field SubResourceIndex

[in] The zero-based index into the resource, which the handle in the <b>hResource</b> member specifies. The <b>SubResourceIndex</b> index indicates the surface. 


## -remarks



DXVAHDDDI_SURFACE structures are used to describe surfaces in members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_videoprocessblthd">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a> structures in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd">VideoProcessBltHD</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_videoprocessblthd">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd">VideoProcessBltHD</a>
 

 

