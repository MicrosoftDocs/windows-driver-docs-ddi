---
UID: NS:d3dkmddi._DXGKARG_ISSUPPORTEDVIDPN
title: _DXGKARG_ISSUPPORTEDVIDPN (d3dkmddi.h)
description: The DXGKARG_ISSUPPORTEDVIDPN structure contains arguments for the DxgkDdiIsSupportedVidPn function. The DxgkDdiIsSupportedVidPn function determines whether a specified video present network (VidPN) is supported on a display adapter.
old-location: display\dxgkarg_issupportedvidpn.htm
ms.assetid: 37f9f40d-6d32-4eeb-8161-282a84ee89dc
ms.date: 05/10/2018
keywords: ["_DXGKARG_ISSUPPORTEDVIDPN structure"]
ms.keywords: "*INOUT_PDXGKARG_ISSUPPORTEDVIDPN, DXGKARG_ISSUPPORTEDVIDPN, DXGKARG_ISSUPPORTEDVIDPN structure [Display Devices], DmStructs_03198868-50e6-47a1-9119-0fa3bff21ec0.xml, _DXGKARG_ISSUPPORTEDVIDPN, d3dkmddi/DXGKARG_ISSUPPORTEDVIDPN, display.dxgkarg_issupportedvidpn"
f1_keywords:
 - "d3dkmddi/DXGKARG_ISSUPPORTEDVIDPN"
 - "DXGKARG_ISSUPPORTEDVIDPN"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGKARG_ISSUPPORTEDVIDPN
targetos: Windows
tech.root: display
req.typenames: DXGKARG_ISSUPPORTEDVIDPN
---

# _DXGKARG_ISSUPPORTEDVIDPN structure


## -description


The DXGKARG_ISSUPPORTEDVIDPN structure contains arguments for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a> function. The <i>DxgkDdiIsSupportedVidPn</i> function determines whether a specified video present network (VidPN) is supported on a display adapter.


## -struct-fields




### -field hDesiredVidPn

A handle to the VidPN object in question.


### -field IsVidPnSupported

A Boolean variable that receives <b>TRUE</b> if the VidPN is supported and <b>FALSE</b> if the VidPN is not supported.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>
 

 

