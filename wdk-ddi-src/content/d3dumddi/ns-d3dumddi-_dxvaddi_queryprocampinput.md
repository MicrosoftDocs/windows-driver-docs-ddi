---
UID: NS:d3dumddi._DXVADDI_QUERYPROCAMPINPUT
title: _DXVADDI_QUERYPROCAMPINPUT (d3dumddi.h)
description: The DXVADDI_QUERYPROCAMPINPUT structure describes a ProcAmp control property on a video stream that range information is requested for.
old-location: display\dxvaddi_queryprocampinput.htm
tech.root: display
ms.assetid: 9ba7c42a-4140-4d8c-abb3-ae5f9285dbd9
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_64cd50ed-940a-46a1-8a4d-b43d40e85b25.xml, DXVADDI_QUERYPROCAMPINPUT, DXVADDI_QUERYPROCAMPINPUT structure [Display Devices], _DXVADDI_QUERYPROCAMPINPUT, d3dumddi/DXVADDI_QUERYPROCAMPINPUT, display.dxvaddi_queryprocampinput
f1_keywords:
 - "d3dumddi/DXVADDI_QUERYPROCAMPINPUT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- DXVADDI_QUERYPROCAMPINPUT
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_QUERYPROCAMPINPUT
---

# _DXVADDI_QUERYPROCAMPINPUT structure


## -description


The DXVADDI_QUERYPROCAMPINPUT structure describes a ProcAmp control property on a video stream that range information is requested for.


## -struct-fields




### -field pVideoProcGuid

[in] A pointer to a GUID that represents the video processing device type. 


### -field VideoDesc

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a> structure that describes the video stream. 


### -field RenderTargetFormat

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.


### -field ProcAmpCap

[in] A ProcAmp control property that range information is requested for. The ProcAmp control property can be one of the members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_procampvalues">DXVADDI_PROCAMPVALUES</a> structure. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_procampvalues">DXVADDI_PROCAMPVALUES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_valuerange">DXVADDI_VALUERANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

