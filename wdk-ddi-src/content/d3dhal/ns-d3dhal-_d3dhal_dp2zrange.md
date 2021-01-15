---
UID: NS:d3dhal._D3DHAL_DP2ZRANGE
title: _D3DHAL_DP2ZRANGE (d3dhal.h)
description: The D3DHAL_DP2ZRANGE structure specifies z-range minimum and maximum in D3dDrawPrimitives2.
old-location: display\d3dhal_dp2zrange.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2ZRANGE structure"]
ms.keywords: "*LPD3DHAL_DP2ZRANGE, D3DHAL_DP2ZRANGE, D3DHAL_DP2ZRANGE structure [Display Devices], LPD3DHAL_DP2ZRANGE, LPD3DHAL_DP2ZRANGE structure pointer [Display Devices], _D3DHAL_DP2ZRANGE, d3dhal/D3DHAL_DP2ZRANGE, d3dhal/LPD3DHAL_DP2ZRANGE, d3dstrct_327e85bf-81c0-420e-b229-e389115fcab3.xml, display.d3dhal_dp2zrange"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
targetos: Windows
req.typenames: D3DHAL_DP2ZRANGE
f1_keywords:
 - _D3DHAL_DP2ZRANGE
 - d3dhal/_D3DHAL_DP2ZRANGE
 - D3DHAL_DP2ZRANGE
 - d3dhal/D3DHAL_DP2ZRANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - _D3DHAL_DP2ZRANGE
 - D3DHAL_DP2ZRANGE
---

# _D3DHAL_DP2ZRANGE structure


## -description

The D3DHAL_DP2ZRANGE structure specifies z-range minimum and maximum in <a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.

## -struct-fields

### -field dvMinZ

Specifies the minimum z value for the Mvs matrix described in the <a href="/windows-hardware/drivers/display/hardware-transform-and-lighting">Hardware Transform and Lighting</a> section of the design guide.

### -field dvMaxZ

Specifies the maximum z value for the Mvs matrix described in the <a href="/windows-hardware/drivers/display/hardware-transform-and-lighting">Hardware Transform and Lighting</a> section of the design guide.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>

