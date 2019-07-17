---
UID: NS:d3dcaps._D3DTRANSFORMCAPS
title: _D3DTRANSFORMCAPS (d3dcaps.h)
description: Obsolete in DirectX 8.0 and later versions. D3DTRANSFORMCAPS structure describes the transform capabilities of a device.
old-location: display\d3dtransformcaps.htm
tech.root: display
ms.assetid: 4eb6c31d-97b2-4d51-ae49-ed2ab395188a
ms.date: 05/10/2018
ms.keywords: "*LPD3DTRANSFORMCAPS, D3DTRANSFORMCAPS, D3DTRANSFORMCAPS structure [Display Devices], LPD3DTRANSFORMCAPS, LPD3DTRANSFORMCAPS structure pointer [Display Devices], _D3DTRANSFORMCAPS, d3dcaps/D3DTRANSFORMCAPS, d3dcaps/LPD3DTRANSFORMCAPS, d3dstrct_9dc73cc8-edfd-424e-b902-0305de356c07.xml, display.d3dtransformcaps"
ms.topic: struct
f1_keywords:
 - "d3dcaps/D3DTRANSFORMCAPS"
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
- D3DTRANSFORMCAPS
product:
- Windows
targetos: Windows
req.typenames: D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS
---

# _D3DTRANSFORMCAPS structure


## -description



   Obsolete in DirectX 8.0 and later versions.
   

D3DTRANSFORMCAPS structure describes the transform capabilities of a device.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the D3DTRANSFORMCAPS structure. 


### -field dwCaps

Specifies flags describing the capabilities of the lighting module. The following flag is defined:

D3DTRANSFORMCAPS_CLIP 
<dl>
<dd>The device can do clipping operations while transforming.</dd>
</dl>



## -remarks



This structure has been replaced by D3DCAPS8 (see the DirectX 8.0 SDK documentation) for DirectX 8.0 and later runtimes, but is required for DirectX 7.0 and earlier runtime compatibility. See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/reporting-directx-8-0-style-direct3d-capabilities">Reporting DirectX 8.0 Style Direct3D Capabilities</a> for details.

This structure is a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3ddevicedesc_v1">D3DDEVICEDESC_V1</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3ddevicedesc_v1">D3DDEVICEDESC_V1</a>
 

 

