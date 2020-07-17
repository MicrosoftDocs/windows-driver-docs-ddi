---
UID: NS:dxgiddi.DXGI_DDI_ARG_PRESENT
title: DXGI_DDI_ARG_PRESENT (dxgiddi.h)
description: The DXGI_DDI_ARG_PRESENT structure describes a resource to display.
old-location: display\dxgi_ddi_arg_present.htm
tech.root: display
ms.assetid: 001cb9fc-d1fa-4ae5-aefd-954d307c4e89
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_PRESENT structure"]
ms.keywords: DXGI_DDI_ARG_PRESENT, DXGI_DDI_ARG_PRESENT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_5ad1821d-dfdb-4361-84dc-48a4a283d66a.xml, display.dxgi_ddi_arg_present, dxgiddi/DXGI_DDI_ARG_PRESENT
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_PRESENT"
 - "DXGI_DDI_ARG_PRESENT"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
- dxgiddi.h
api_name:
- DXGI_DDI_ARG_PRESENT
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_PRESENT
---

# DXGI_DDI_ARG_PRESENT structure


## -description


The DXGI_DDI_ARG_PRESENT structure describes a resource to display. 


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device. 


### -field hSurfaceToPresent

[in] A handle to the source resource to display. <b>hSurfaceToPresent</b> is always a valid handle for a resource to display.



### -field SrcSubResourceIndex

[in] The zero-based index into the source resource, which the handle in the <b>hSurfaceToPresent</b> member specifies. The <b>SrcSubResourceIndex</b> index indicates the subresource or surface to display.


### -field hDstResource

[in] A handle to the destination resource to display to. <b>hDstResource</b> can be <b>NULL</b> if the destination is unknown; kernel mode will determine the destination just before sending the hardware command stream through DMA to the graphics processor.


### -field DstSubResourceIndex


      [in] The zero-based index into the destination resource, which the handle in the <b>hDstResource</b> member specifies. The <b>DstSubResourceIndex</b> index indicates the subresource or surface to display to.
     


### -field pDXGIContext

[in] A handle to the DXGI context. This handle is opaque to the driver. The driver must pass the handle in this member as the <b>pDXGIContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a> structure when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_presentcb">pfnPresentCbDXGI</a> function. 


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_present_flags">DXGI_DDI_PRESENT_FLAGS</a> structure that identifies, in bit-field flags, how to perform the present operation. 


### -field FlipInterval

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_flip_interval_type">DXGI_DDI_FLIP_INTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs).


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_flip_interval_type">DXGI_DDI_FLIP_INTERVAL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_present_flags">DXGI_DDI_PRESENT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_presentcb">pfnPresentCbDXGI</a>
 

 

