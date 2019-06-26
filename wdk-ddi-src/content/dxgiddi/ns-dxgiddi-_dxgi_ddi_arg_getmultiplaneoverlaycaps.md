---
UID: NS:dxgiddi._DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
title: _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS (dxgiddi.h)
description: Used in a call to the pfnGetMultiPlaneOverlayCaps function to get overlay plane capabilities.
old-location: display\dxgi_ddi_arg_getmultiplaneoverlaycaps.htm
tech.root: display
ms.assetid: 7e4f9610-52f4-4807-94f0-c408ecb0673c
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS, DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS structure [Display Devices], _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS, display.dxgi_ddi_arg_getmultiplaneoverlaycaps, dxgiddi/DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dxgiddi.h
api_name:
- DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
---

# _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS structure


## -description


Used in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">pfnGetMultiPlaneOverlayCaps</a> function to get overlay plane capabilities.


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) for which overlay plane capabilities are needed.

The Direct3D runtime passed this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when it created the device by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> routine.


### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the capabilities are queried.


### -field MultiplaneOverlayCaps

[out] The overlay plane capabilities, given as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-dxgi_ddi_multiplane_overlay_caps">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-dxgi_ddi_multiplane_overlay_caps">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">pfnGetMultiPlaneOverlayCaps</a>
 

 

