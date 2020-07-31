---
UID: NS:dxgiddi._DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
title: _DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY (dxgiddi.h)
description: Specifies a multiplane overlay resource to display.
old-location: display\dxgi_ddi_arg_presentmultiplaneoverlay.htm
tech.root: display
ms.assetid: 3d965c9b-1d71-4ef5-9b76-391b36b1d8c7
ms.date: 05/10/2018
keywords: ["_DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure"]
ms.keywords: DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY, DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure [Display Devices], _DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY, display.dxgi_ddi_arg_presentmultiplaneoverlay, dxgiddi/DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY"
 - "DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY"
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
- DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
targetos: Windows
req.typenames: DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
---

# _DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure


## -description


Specifies a multiplane overlay resource to display.


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device. 


### -field pDXGIContext

[in] A handle to the DXGI context. This handle is opaque to the driver. The driver should assign the handle in this member to the <b>pDXGIContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present_multiplane_overlay">DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY</a> structure when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function. 


### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_present_flags">DXGI_DDI_PRESENT_FLAGS</a> structure that identifies, in bit-field flags, how to display.


### -field FlipInterval

[in] A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_flip_interval_type">DXGI_DDI_FLIP_INTERVAL_TYPE</a> that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


### -field PresentPlaneCount

[in] The number of overlay planes that are available to display.


### -field pPresentPlanes

[in] A pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-_dxgi_ddi_present_multiplane_overlay">DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY</a> that  describes the overlay plane to display.


### -field Reserved

This member is reserved and should be set to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present_multiplane_overlay">DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_flip_interval_type">DXGI_DDI_FLIP_INTERVAL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_present_flags">DXGI_DDI_PRESENT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-_dxgi_ddi_present_multiplane_overlay">DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb">pfnPresentMultiPlaneOverlayCb (DXGI)</a>
 

 

