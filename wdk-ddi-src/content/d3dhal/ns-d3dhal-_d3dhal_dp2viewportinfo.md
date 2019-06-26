---
UID: NS:d3dhal._D3DHAL_DP2VIEWPORTINFO
title: _D3DHAL_DP2VIEWPORTINFO (d3dhal.h)
description: The D3DHAL_DP2VIEWPORTINFO structure is used to inform guard-band aware drivers of the view clipping rectangle. The clipping rectangle is specified by the members dwX, dwY, dwWidth and dwHeight.
old-location: display\d3dhal_dp2viewportinfo.htm
tech.root: display
ms.assetid: df46a37e-fed6-4738-8794-6611e9c758cb
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2VIEWPORTINFO, D3DHAL_DP2VIEWPORTINFO, D3DHAL_DP2VIEWPORTINFO structure [Display Devices], LPD3DHAL_DP2VIEWPORTINFO, LPD3DHAL_DP2VIEWPORTINFO structure pointer [Display Devices], _D3DHAL_DP2VIEWPORTINFO, d3dhal/D3DHAL_DP2VIEWPORTINFO, d3dhal/LPD3DHAL_DP2VIEWPORTINFO, d3dstrct_7a7ca4d1-eb1a-4342-9ce9-f4b276191da5.xml, display.d3dhal_dp2viewportinfo"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2VIEWPORTINFO
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2VIEWPORTINFO
---

# _D3DHAL_DP2VIEWPORTINFO structure


## -description


The D3DHAL_DP2VIEWPORTINFO structure is used to inform guard-band aware drivers of the view clipping rectangle. The clipping rectangle is specified by the members <b>dwX</b>, <b>dwY</b>, <b>dwWidth</b> and <b>dwHeight</b>.


## -struct-fields




### -field dwX


### -field dwY

Specify the location, in screen coordinates, of the upper-left corner of the subrectangle.


### -field dwWidth


### -field dwHeight

Specify the width and height, respectively, of the subrectangle where the application is rendering. These members are specified in screen coordinates.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback parses a D3DHAL_DP2VIEWPORTINFO structure from the command buffer and updates the driver's viewport description when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> is set to D3DDP2OP_VIEWPORTINFO.

One D3DHAL_DP2VIEWPORTINFO structure follows the D3DHAL_DP2COMMAND structure in the command buffer.

The driver should update the viewport portion of its internal rendering context with the location and size values specified in this structure. The driver can use this information to perform guard band clipping.

Subguard-band drivers should ignore and skip over these instructions and continue processing the rest of the command buffer.




## -see-also




D3DDP2OP_VIEWPORTINFO



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

