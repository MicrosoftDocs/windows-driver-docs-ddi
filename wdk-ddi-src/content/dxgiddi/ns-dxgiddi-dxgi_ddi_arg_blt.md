---
UID: NS:dxgiddi.DXGI_DDI_ARG_BLT
title: DXGI_DDI_ARG_BLT (dxgiddi.h)
description: The DXGI_DDI_ARG_BLT structure describes the parameters of a bit-block transfer (bitblt).
old-location: display\dxgi_ddi_arg_blt.htm
tech.root: display
ms.assetid: 695f2aff-cce3-4358-a9e2-48eea43e8ef5
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_BLT structure"]
ms.keywords: DXGI_DDI_ARG_BLT, DXGI_DDI_ARG_BLT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_299fa1c4-8c06-4a7e-a81c-741eb2e8c00a.xml, display.dxgi_ddi_arg_blt, dxgiddi/DXGI_DDI_ARG_BLT
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_BLT"
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
- DXGI_DDI_ARG_BLT
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_BLT
---

# DXGI_DDI_ARG_BLT structure


## -description


The <b>DXGI_DDI_ARG_BLT</b> structure describes the parameters of a bit-block transfer (bitblt). 


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the bitblt. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device. 


### -field hDstResource

[in] A handle to the destination resource. 


### -field DstSubresource

[in] The index to the destination surface within the resource. 


### -field DstLeft

[in] The <i>x</i>-coordinate of the upper-left corner of the destination rectangle. 


### -field DstTop

[in] The <i>y</i>-coordinate of the upper-left corner of the destination rectangle. 


### -field DstRight

[in] The <i>x</i>-coordinate of the lower-right corner of the destination rectangle. 


### -field DstBottom

[in] The <i>y</i>-coordinate of the lower-right corner of the destination rectangle. 


### -field hSrcResource

[in] A handle to the source resource. 


### -field SrcSubresource

[in] The index to the source surface within the resource. 


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt_flags">DXGI_DDI_ARG_BLT_FLAGS</a> structure that identifies the type of bitblt to perform. 


### -field Rotate

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_mode_rotation">DXGI_DDI_MODE_ROTATION</a>-typed value that identifies the orientation of the display mode.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt_flags">DXGI_DDI_ARG_BLT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_mode_rotation">DXGI_DDI_MODE_ROTATION</a>
 

 

