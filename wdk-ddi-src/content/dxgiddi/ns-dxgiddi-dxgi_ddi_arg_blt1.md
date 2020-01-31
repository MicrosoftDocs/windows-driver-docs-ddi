---
UID: NS:dxgiddi.DXGI_DDI_ARG_BLT1
title: DXGI_DDI_ARG_BLT1 (dxgiddi.h)
description: Describes the parameters of a bit-block transfer (bitblt) that include specifications for a source rectangle. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\dxgi_ddi_arg_blt1.htm
tech.root: display
ms.assetid: bc7c2693-6a18-4335-8921-363981a830f1
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_ARG_BLT1, DXGI_DDI_ARG_BLT1 structure [Display Devices], display.dxgi_ddi_arg_blt1, dxgiddi/DXGI_DDI_ARG_BLT1
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_BLT1"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,WDDM 1.2 and later
req.target-min-winversvr: Windows Server 2012
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
- DXGI_DDI_ARG_BLT1
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_BLT1
---

# DXGI_DDI_ARG_BLT1 structure


## -description


Describes the parameters of a bit-block transfer (bitblt) that include specifications for a  source rectangle. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


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


### -field SrcLeft

[in] The <i>x</i>-coordinate of the upper-left corner of the source rectangle.


### -field SrcTop

[in] The <i>y</i>-coordinate of the upper-left corner of the source rectangle. 


### -field SrcRight

[in] The <i>x</i>-coordinate of the lower-right corner of the source rectangle.


### -field SrcBottom

[in] The <i>y</i>-coordinate of the lower-right corner of the destination rectangle.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt_flags">DXGI_DDI_ARG_BLT_FLAGS</a> structure that identifies the type of bitblt to perform. 


### -field Rotate

[in] A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_mode_rotation">DXGI_DDI_MODE_ROTATION</a> that identifies the orientation of the display mode.


## -remarks



The source rectangle specified by the members <b>SrcLeft</b>, <b>SrcTop</b>, <b>SrcRight</b>, and <b>SrcBottom</b> is typically a dirty subrectangle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt_flags">DXGI_DDI_ARG_BLT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_mode_rotation">DXGI_DDI_MODE_ROTATION</a>
 

 

