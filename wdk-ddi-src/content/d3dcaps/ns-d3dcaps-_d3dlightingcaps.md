---
UID: NS:d3dcaps._D3DLIGHTINGCAPS
title: _D3DLIGHTINGCAPS (d3dcaps.h)
description: Obsolete in DirectX 8.0 and later versions; see Remarks. The D3DLIGHTINGCAPS structure describes the lighting capabilities of a device.
old-location: display\d3dlightingcaps.htm
tech.root: display
ms.assetid: ea8ba463-e8dd-4952-bcad-6fe565fe3292
ms.date: 05/10/2018
ms.keywords: "*LPD3DLIGHTINGCAPS, D3DLIGHTINGCAPS, D3DLIGHTINGCAPS structure [Display Devices], LPD3DLIGHTINGCAPS, LPD3DLIGHTINGCAPS structure pointer [Display Devices], _D3DLIGHTINGCAPS, d3dcaps/D3DLIGHTINGCAPS, d3dcaps/LPD3DLIGHTINGCAPS, d3dstrct_98470d9f-b4ed-49ee-9c0f-34c991916de3.xml, display.d3dlightingcaps"
ms.topic: struct
f1_keywords:
 - "d3dcaps/D3DLIGHTINGCAPS"
req.header: d3dcaps.h
req.include-header: D3dcaps.h
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
- d3dcaps.h
api_name:
- D3DLIGHTINGCAPS
product:
- Windows
targetos: Windows
req.typenames: D3DLIGHTINGCAPS, *LPD3DLIGHTINGCAPS
---

# _D3DLIGHTINGCAPS structure


## -description



   Obsolete in DirectX 8.0 and later versions; see Remarks.
   

The D3DLIGHTINGCAPS structure describes the lighting capabilities of a device.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the D3DLIGHTINGCAPS structure. 


### -field dwCaps

 Specifies flags describing the capabilities of the lighting module. The following flags are defined:   


|Value|Meaning|
|--- |--- |
|D3DLIGHTCAPS_DIRECTIONAL|Directional lights are supported.|
|D3DLIGHTCAPS_GLSPOT|OpenGL-style spotlights are supported.|
|D3DLIGHTCAPS_PARALLELPOINT|Parallel-point lights are supported.|
|D3DLIGHTCAPS_POINT|Point lights are supported.|
|D3DLIGHTCAPS_SPOT|Spotlights are supported.|
 


### -field dwLightingModel

 Specifies flags indicating whether the lighting model is RGB or monochrome. The following flags are defined: 

|Value|Meaning|
|--- |--- |
|D3DLIGHTINGMODEL_MONO|The lighting model is monochromatic.|
|D3DLIGHTINGMODEL_RGB|The lighting model is RGB.|
 


### -field dwNumLights

Specifies the number of lights that can be handled.


## -remarks



This structure has been replaced by D3DCAPS8 (see the DirectX 8.0 SDK documentation) for DirectX 8.0 and later runtimes, but is required for DirectX 7.0 and earlier runtime compatibility. See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/reporting-directx-8-0-style-direct3d-capabilities">Reporting DirectX 8.0 Style Direct3D Capabilities</a> for details.

This structure is a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3ddevicedesc_v1">D3DDEVICEDESC_V1</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3ddevicedesc_v1">D3DDEVICEDESC_V1</a>
 

 

