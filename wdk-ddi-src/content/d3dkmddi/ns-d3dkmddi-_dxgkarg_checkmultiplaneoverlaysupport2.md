---
UID: NS:d3dkmddi._DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2
title: _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 (d3dkmddi.h)
description: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 is passed to the DxgkDdiCheckMultiPlaneOverlaySupport2 function to determine whether a specific multi-plane overlay configuration is supported.
old-location: display\dxgkarg_checkmultiplaneoverlaysupport2.htm
ms.assetid: 477EBC8A-04A5-4904-AC62-0FA7DB861ACC
ms.date: 05/10/2018
keywords: ["_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 structure"]
ms.keywords: "*IN_OUT_PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 structure [Display Devices], _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2, display.dxgkarg_checkmultiplaneoverlaysupport2"
f1_keywords:
 - "d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- d3dkmddi.h
api_name:
- DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2
---

# _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 structure


## -description


<b>DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2</b> is passed to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2">DxgkDdiCheckMultiPlaneOverlaySupport2</a> function to determine whether a specific multi-plane overlay configuration is supported. 


## -struct-fields




### -field PlaneCount

The number of planes to be enabled.


### -field pPlanes

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_plane_with_source">DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE</a> 
                                                                        structure that specifies support attributes that the hardware
                                                                        provides for multi-plane overlays.


### -field Supported

<b>TRUE</b> if the multi-plane overlay configuration can be supported, otherwise <b>FALSE</b>.


### -field ReturnInfo

Specifies additional information.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_plane_with_source">DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2">DxgkDdiCheckMultiPlaneOverlaySupport2</a>
 

 

