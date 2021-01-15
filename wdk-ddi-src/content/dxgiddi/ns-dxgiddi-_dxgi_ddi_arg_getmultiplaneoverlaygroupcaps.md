---
UID: NS:dxgiddi._DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
title: _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS (dxgiddi.h)
description: Used in a call to the pfnGetMultiplaneOverlayGroupCaps function to get a group of overlay plane capabilities.
old-location: display\dxgi_ddi_arg_getmultiplaneoverlaygroupcaps.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS structure"]
ms.keywords: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS, DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS structure [Display Devices], _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS, display.dxgi_ddi_arg_getmultiplaneoverlaygroupcaps, dxgiddi/DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
f1_keywords:
 - _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
 - dxgiddi/_DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
 - DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
 - dxgiddi/DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dxgiddi.h
api_name:
 - _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
 - DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
---

# _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS structure


## -description

Used in a call to the <a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">pfnGetMultiplaneOverlayGroupCaps</a> function to get a group of overlay plane capabilities.

## -struct-fields

### -field hDevice

[in] A handle to the display device (graphics context) for which overlay plane capabilities are needed.

The Direct3D runtime passed this handle to the driver in the <b>hDrvDevice</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when it created the device by calling the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> routine.

### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the capabilities are queried.

### -field GroupIndex

[in] The index of the overlay capability group for which capabilities are queried. This value is always between zero and (<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_multiplane_overlay_caps">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a>.<b>NumCapabilityGroups</b> – 1).

### -field MultiplaneOverlayGroupCaps

[out] The overlay plane capabilities for the requested capability group, given as a <a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_multiplane_overlay_group_caps">DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_multiplane_overlay_caps">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_multiplane_overlay_group_caps">DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">pfnGetMultiplaneOverlayGroupCaps</a>

