---
UID: NS:d3dhal._D3DHAL_DP2VIEWPORTINFO
title: "_D3DHAL_DP2VIEWPORTINFO"
author: windows-driver-content
description: The D3DHAL_DP2VIEWPORTINFO structure is used to inform guard-band aware drivers of the view clipping rectangle. The clipping rectangle is specified by the members dwX, dwY, dwWidth and dwHeight.
old-location: display\d3dhal_dp2viewportinfo.htm
old-project: display
ms.assetid: df46a37e-fed6-4738-8794-6611e9c758cb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2VIEWPORTINFO, D3DHAL_DP2VIEWPORTINFO, D3DHAL_DP2VIEWPORTINFO structure [Display Devices], LPD3DHAL_DP2VIEWPORTINFO, LPD3DHAL_DP2VIEWPORTINFO structure pointer [Display Devices], _D3DHAL_DP2VIEWPORTINFO, d3dhal/D3DHAL_DP2VIEWPORTINFO, d3dhal/LPD3DHAL_DP2VIEWPORTINFO, d3dstrct_7a7ca4d1-eb1a-4342-9ce9-f4b276191da5.xml, display.d3dhal_dp2viewportinfo"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2VIEWPORTINFO
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2VIEWPORTINFO
---

# _D3DHAL_DP2VIEWPORTINFO structure


## -description


The D3DHAL_DP2VIEWPORTINFO structure is used to inform guard-band aware drivers of the view clipping rectangle. The clipping rectangle is specified by the members <b>dwX</b>, <b>dwY</b>, <b>dwWidth</b> and <b>dwHeight</b>.


## -syntax


````
typedef struct _D3DHAL_DP2VIEWPORTINFO {
  DWORD dwX;
  DWORD dwY;
  DWORD dwWidth;
  DWORD dwHeight;
} D3DHAL_DP2VIEWPORTINFO, *LPD3DHAL_DP2VIEWPORTINFO;
````


## -struct-fields




### -field dwX


### -field dwY

Specify the location, in screen coordinates, of the upper-left corner of the subrectangle.


### -field dwWidth


### -field dwHeight

Specify the width and height, respectively, of the subrectangle where the application is rendering. These members are specified in screen coordinates.


## -remarks



The <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback parses a D3DHAL_DP2VIEWPORTINFO structure from the command buffer and updates the driver's viewport description when <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> is set to D3DDP2OP_VIEWPORTINFO.

One D3DHAL_DP2VIEWPORTINFO structure follows the D3DHAL_DP2COMMAND structure in the command buffer.

The driver should update the viewport portion of its internal rendering context with the location and size values specified in this structure. The driver can use this information to perform guard band clipping.

Subguard-band drivers should ignore and skip over these instructions and continue processing the rest of the command buffer.




## -see-also

D3DDP2OP_VIEWPORTINFO



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2VIEWPORTINFO structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

