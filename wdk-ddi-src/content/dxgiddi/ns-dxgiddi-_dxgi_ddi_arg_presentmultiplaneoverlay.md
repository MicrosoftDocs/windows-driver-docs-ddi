---
UID: NS:dxgiddi._DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
title: "_DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY"
author: windows-driver-content
description: Specifies a multiplane overlay resource to display.
old-location: display\dxgi_ddi_arg_presentmultiplaneoverlay.htm
old-project: display
ms.assetid: 3d965c9b-1d71-4ef5-9b76-391b36b1d8c7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY, DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure [Display Devices], _DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY, display.dxgi_ddi_arg_presentmultiplaneoverlay, dxgiddi/DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
---

# _DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure


## -description


Specifies a multiplane overlay resource to display.


## -syntax


````
typedef struct _DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY {
  DXGI_DDI_HDEVICE                    hDevice;
  void                                *pDXGIContext;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID      VidPnSourceId;
  DXGI_DDI_PRESENT_FLAGS              Flags;
  DXGI_DDI_FLIP_INTERVAL_TYPE         FlipInterval;
  UINT                                PresentPlaneCount;
  DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY *pPresentPlanes;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  UINT                                Reserved;
#endif 
} DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


### -field pDXGIContext

[in] A handle to the DXGI context. This handle is opaque to the driver. The driver should assign the handle in this member to the <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present_multiplane_overlay.md">DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY</a> structure when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780324">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function. 


### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.


### -field Flags

[in] A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_present_flags.md">DXGI_DDI_PRESENT_FLAGS</a> structure that identifies, in bit-field flags, how to display.


### -field FlipInterval

[in] A value of type <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_flip_interval_type.md">DXGI_DDI_FLIP_INTERVAL_TYPE</a> that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


### -field PresentPlaneCount

[in] The number of overlay planes that are available to display.


### -field pPresentPlanes

[in] A pointer to a structure of type <a href="..\dxgiddi\ns-dxgiddi-_dxgi_ddi_present_multiplane_overlay.md">DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY</a> that  describes the overlay plane to display.


### -field Reserved

This member is reserved and should be set to zero.


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_present_flags.md">DXGI_DDI_PRESENT_FLAGS</a>



<a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_flip_interval_type.md">DXGI_DDI_FLIP_INTERVAL_TYPE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present_multiplane_overlay.md">DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780324">pfnPresentMultiPlaneOverlayCb (DXGI)</a>



<a href="..\dxgiddi\ns-dxgiddi-_dxgi_ddi_present_multiplane_overlay.md">DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

