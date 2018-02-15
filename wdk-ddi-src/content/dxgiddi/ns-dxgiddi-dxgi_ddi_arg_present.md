---
UID: NS:dxgiddi.DXGI_DDI_ARG_PRESENT
title: DXGI_DDI_ARG_PRESENT
author: windows-driver-content
description: The DXGI_DDI_ARG_PRESENT structure describes a resource to display.
old-location: display\dxgi_ddi_arg_present.htm
old-project: display
ms.assetid: 001cb9fc-d1fa-4ae5-aefd-954d307c4e89
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_ARG_PRESENT, DXGI_DDI_ARG_PRESENT structure [Display Devices], dxgiddi/DXGI_DDI_ARG_PRESENT, display.dxgi_ddi_arg_present, UMDisplayDriver_Dx10param_Structs_5ad1821d-dfdb-4361-84dc-48a4a283d66a.xml
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
-	DXGI_DDI_ARG_PRESENT
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_PRESENT
---

# DXGI_DDI_ARG_PRESENT structure


## -description


The DXGI_DDI_ARG_PRESENT structure describes a resource to display. 


## -syntax


````
typedef struct DXGI_DDI_ARG_PRESENT {
  DXGI_DDI_HDEVICE            hDevice;
  DXGI_DDI_HRESOURCE          hSurfaceToPresent;
  UINT                        SrcSubResourceIndex;
  DXGI_DDI_HRESOURCE          hDstResource;
  UINT                        DstSubResourceIndex;
  void                        *pDXGIContext;
  DXGI_DDI_PRESENT_FLAGS      Flags;
  DXGI_DDI_FLIP_INTERVAL_TYPE FlipInterval;
} DXGI_DDI_ARG_PRESENT;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


### -field hSurfaceToPresent

[in] A handle to the source resource to display. <b>hSurfaceToPresent</b> is always a valid handle for a resource to display.



### -field SrcSubResourceIndex

[in] The zero-based index into the source resource, which the handle in the <b>hSurfaceToPresent</b> member specifies. The <b>SrcSubResourceIndex</b> index indicates the subresource or surface to display.


### -field hDstResource

[in] A handle to the destination resource to display to. <b>hDstResource</b> can be <b>NULL</b> if the destination is unknown; kernel mode will determine the destination just before sending the hardware command stream through DMA to the graphics processor.


### -field DstSubResourceIndex


      [in] The zero-based index into the destination resource, which the handle in the <b>hDstResource</b> member specifies. The <b>DstSubResourceIndex</b> index indicates the subresource or surface to display to.
     


### -field pDXGIContext

[in] A handle to the DXGI context. This handle is opaque to the driver. The driver must pass the handle in this member as the <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present.md">DXGIDDICB_PRESENT</a> structure when the driver calls the <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a> function. 


### -field Flags

[in] A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_present_flags.md">DXGI_DDI_PRESENT_FLAGS</a> structure that identifies, in bit-field flags, how to perform the present operation. 


### -field FlipInterval

[in] A <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_flip_interval_type.md">DXGI_DDI_FLIP_INTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs).


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present.md">DXGIDDICB_PRESENT</a>



<a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_flip_interval_type.md">DXGI_DDI_FLIP_INTERVAL_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_present_flags.md">DXGI_DDI_PRESENT_FLAGS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_PRESENT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

