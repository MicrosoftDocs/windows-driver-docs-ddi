---
UID: NS:dxgiddi.DXGI_DDI_ARG_BLT
title: DXGI_DDI_ARG_BLT
author: windows-driver-content
description: The DXGI_DDI_ARG_BLT structure describes the parameters of a bit-block transfer (bitblt).
old-location: display\dxgi_ddi_arg_blt.htm
old-project: display
ms.assetid: 695f2aff-cce3-4358-a9e2-48eea43e8ef5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_Dx10param_Structs_299fa1c4-8c06-4a7e-a81c-741eb2e8c00a.xml, dxgiddi/DXGI_DDI_ARG_BLT, display.dxgi_ddi_arg_blt, DXGI_DDI_ARG_BLT structure [Display Devices], DXGI_DDI_ARG_BLT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxgiddi.h
apiname:
-	DXGI_DDI_ARG_BLT
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_BLT
---

# DXGI_DDI_ARG_BLT structure


## -description


The <b>DXGI_DDI_ARG_BLT</b> structure describes the parameters of a bit-block transfer (bitblt). 


## -syntax


````
typedef struct DXGI_DDI_ARG_BLT {
  DXGI_DDI_HDEVICE       hDevice;
  DXGI_DDI_HRESOURCE     hDstResource;
  UINT                   DstSubresource;
  UINT                   DstLeft;
  UINT                   DstTop;
  UINT                   DstRight;
  UINT                   DstBottom;
  DXGI_DDI_HRESOURCE     hSrcResource;
  UINT                   SrcSubresource;
  DXGI_DDI_ARG_BLT_FLAGS Flags;
  DXGI_DDI_MODE_ROTATION Rotate;
} DXGI_DDI_ARG_BLT;
````


## -struct-fields




#### - hDevice

[in] A handle to the display device (graphics context) on which the driver performs the bitblt. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


#### - hDstResource

[in] A handle to the destination resource. 


#### - DstSubresource

[in] The index to the destination surface within the resource. 


#### - DstLeft

[in] The <i>x</i>-coordinate of the upper-left corner of the destination rectangle. 


#### - DstTop

[in] The <i>y</i>-coordinate of the upper-left corner of the destination rectangle. 


#### - DstRight

[in] The <i>x</i>-coordinate of the lower-right corner of the destination rectangle. 


#### - DstBottom

[in] The <i>y</i>-coordinate of the lower-right corner of the destination rectangle. 


#### - hSrcResource

[in] A handle to the source resource. 


#### - SrcSubresource

[in] The index to the source surface within the resource. 


#### - Flags

[in] A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_blt_flags.md">DXGI_DDI_ARG_BLT_FLAGS</a> structure that identifies the type of bitblt to perform. 


#### - Rotate

[in] A <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_rotation.md">DXGI_DDI_MODE_ROTATION</a>-typed value that identifies the orientation of the display mode.


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_blt_flags.md">DXGI_DDI_ARG_BLT_FLAGS</a>

<a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_rotation.md">DXGI_DDI_MODE_ROTATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_BLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

