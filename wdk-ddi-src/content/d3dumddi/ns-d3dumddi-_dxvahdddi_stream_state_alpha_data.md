---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_ALPHA_DATA
title: _DXVAHDDDI_STREAM_STATE_ALPHA_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure describes stream-state data that specifies the alpha blend level per-plane.
old-location: display\dxvahdddi_stream_state_alpha_data.htm
tech.root: display
ms.assetid: 0cd14f0c-5b7b-443b-ab37-c455b4accacb
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_33a16800-e101-40e7-b776-36161a8a984a.xml, DXVAHDDDI_STREAM_STATE_ALPHA_DATA, DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_ALPHA_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_ALPHA_DATA, display.dxvahdddi_stream_state_alpha_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_STATE_ALPHA_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_ALPHA_DATA is supported beginning with the Windows 7 operating system.
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
- DXVAHDDDI_STREAM_STATE_ALPHA_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_ALPHA_DATA
---

# _DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure describes stream-state data that specifies the alpha blend level per-plane. 


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the driver should alpha blend. The default value is <b>FALSE</b>, which indicates that alpha blend is disabled. 


### -field Alpha

[in] A FLOAT value in the 0.0 to 1.0 range that describes the alpha level (that is, the transparency level). The default value is 1.0 for opaque. 


## -remarks



The driver multiplies the alpha value with each source pixel and blends the result with the destination pixel. For example, the driver uses the following values to perform the following calculation:

Cs = source pixel color value

Cd = destination pixel color value

As = per-pixel source alpha value [0.0, 1.0]

Ap = per-plane alpha value [0.0, 1.0]

Ae = per-entry palette alpha value [0.0, 1.0] or 1.0 if the driver did not set the DXVAHDDDI_FEATURE_CAPS_ALPHA_PALETTE value in the <b>FeatureCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set.

Cd = Cs * (As * Ap * Ae) + Cd * (1.0 - As * Ap * Ae)

Ad = per-pixel destination alpha value [0.0, 1.0]

The Ad parameter is set with values from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_alpha_fill_mode">DXVAHDDDI_ALPHA_FILL_MODE</a> enumeration.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_alpha_fill_mode">DXVAHDDDI_ALPHA_FILL_MODE</a>
 

 

