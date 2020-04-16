---
UID: NS:dxgiddi.DXGI_DDI_ARG_PRESENT1
title: DXGI_DDI_ARG_PRESENT1 (dxgiddi.h)
description: Describes a resource to display. Used with the pfnPresent1(DXGI) function by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\dxgi_ddi_arg_present1.htm
tech.root: display
ms.assetid: F8575652-CA6D-472E-A314-91B07C48558B
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_PRESENT1 structure"]
ms.keywords: DXGI_DDI_ARG_PRESENT1, DXGI_DDI_ARG_PRESENT1 structure [Display Devices], display.dxgi_ddi_arg_present1, dxgiddi/DXGI_DDI_ARG_PRESENT1
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_PRESENT1"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
- DXGI_DDI_ARG_PRESENT1
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_PRESENT1
---

# DXGI_DDI_ARG_PRESENT1 structure


## -description


Describes a resource to display. Used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_3_ddi_base_functions">pfnPresent1(DXGI)</a> function by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.



## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device. 

### -field phSurfacesToPresent

[in] An array of non-<b>NULL</b> handles and zero-based indices to the source resource to display or to release. <b>phSurfacesToPresent</b> is always a valid handle for a resource to display.


### -field SurfacesToPresent

[in] The array of surfaces to be presented. Must not be zero.


### -field hDstResource

[in] A handle to the destination resource to display to. <b>hDstResource</b> can be <b>NULL</b> if the destination is unknown; kernel mode will determine the destination just before sending the hardware command stream through DMA to the graphics processor.

When many resource are being presented, <b>hDstResource</b> will be <b>NULL</b>, and the driver must only translate the last source resource handle for use with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentcb">pfnPresentCb</a> function.


### -field DstSubResourceIndex


[in] The zero-based index into the destination resource, which the handle in the <b>hDstResource</b> member specifies. The <b>DstSubResourceIndex</b> index indicates the subresource or surface to display to.


### -field pDXGIContext

[in] A handle to the DXGI context. This handle is opaque to the driver. The driver must pass the handle in this member as the <b>pDXGIContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a> structure when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_presentcb">pfnPresentCbDXGI</a> function. 


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_present_flags">DXGI_DDI_PRESENT_FLAGS</a> structure that identifies, in bit-field flags, how to perform the present operation. 


### -field FlipInterval

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_flip_interval_type">DXGI_DDI_FLIP_INTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs).


### -field Reserved

This member is reserved and should be set to zero.


### -field pDirtyRects

[in] A pointer to an array of dirty rectangles (<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>s), relative to the source rectangle <b>SrcRect</b>, that indicate the portion of the overlay plane that has changed.

The driver can use this member to perform optimizations, though it's not required to use the dirty rectangle info. However, the driver should never fail a function call based on the provided dirty rectangles.


### -field DirtyRects

[in] The number of dirty rectangles in the array pointed to by <b>pDirtyRects</b>.


### -field BackBufferMultiplicity

The number of physical back buffer per logical back buffer.



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_flip_interval_type">DXGI_DDI_FLIP_INTERVAL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_present_flags">DXGI_DDI_PRESENT_FLAGS</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_3_ddi_base_functions">pfnPresent1(DXGI)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentcb">pfnPresentCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_presentcb">pfnPresentCbDXGI</a>
 

 

