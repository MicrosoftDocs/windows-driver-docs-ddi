---
UID: NS:d3dcaps._D3DLIGHTINGCAPS
title: "_D3DLIGHTINGCAPS"
author: windows-driver-content
description: Obsolete in DirectX 8.0 and later versions; see Remarks. The D3DLIGHTINGCAPS structure describes the lighting capabilities of a device.
old-location: display\d3dlightingcaps.htm
old-project: display
ms.assetid: ea8ba463-e8dd-4952-bcad-6fe565fe3292
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DLIGHTINGCAPS, D3DLIGHTINGCAPS, D3DLIGHTINGCAPS structure [Display Devices], LPD3DLIGHTINGCAPS, LPD3DLIGHTINGCAPS structure pointer [Display Devices], _D3DLIGHTINGCAPS, d3dcaps/D3DLIGHTINGCAPS, d3dcaps/LPD3DLIGHTINGCAPS, d3dstrct_98470d9f-b4ed-49ee-9c0f-34c991916de3.xml, display.d3dlightingcaps"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dcaps.h
api_name:
-	D3DLIGHTINGCAPS
product: Windows
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
  
  
  

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>D3DLIGHTCAPS_DIRECTIONAL</td>
<td>Directional lights are supported. 
</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_GLSPOT</td>
<td>OpenGL-style spotlights are supported.</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_PARALLELPOINT</td>
<td>Parallel-point lights are supported.</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_POINT</td>
<td>Point lights are supported.</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_SPOT</td>
<td>Spotlights are supported. 
</td>
</tr>
</table>
 


### -field dwLightingModel

 Specifies flags indicating whether the lighting model is RGB or monochrome. The following flags are defined: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>D3DLIGHTINGMODEL_MONO </td>
<td>The lighting model is monochromatic. 
 </td>
</tr>
<tr>
<td>D3DLIGHTINGMODEL_RGB</td>
<td>The lighting model is RGB. 
</td>
</tr>
</table>
 


### -field dwNumLights

Specifies the number of lights that can be handled.


## -remarks



This structure has been replaced by D3DCAPS8 (see the DirectX 8.0 SDK documentation) for DirectX 8.0 and later runtimes, but is required for DirectX 7.0 and earlier runtime compatibility. See <a href="https://msdn.microsoft.com/a03a7cbc-95be-4251-8e3a-bef4a093f03d">Reporting DirectX 8.0 Style Direct3D Capabilities</a> for details.

This structure is a member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544689">D3DDEVICEDESC_V1</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544689">D3DDEVICEDESC_V1</a>
 

 

