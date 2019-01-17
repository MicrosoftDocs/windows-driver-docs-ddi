---
UID: NS:dxgiddi._DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT
title: "_DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT"
description: Used in a call to the pfnCheckMultiPlaneOverlaySupport (DXGI) function to check details on hardware support for multiplane overlays.
old-location: display\dxgi_ddi_arg_checkmultiplaneoverlaysupport.htm
tech.root: display
ms.assetid: 1b339a88-9c05-4b57-9044-b00ef1c305fb
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT structure [Display Devices], _DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT, display.dxgi_ddi_arg_checkmultiplaneoverlaysupport, dxgiddi/DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT
ms.topic: struct
req.header: dxgiddi.h
req.include-header: Dxgiddi.h
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
-	DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT
---

# _DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT structure


## -description


Used in a call to the <a href="https://msdn.microsoft.com/9062BB6D-7B52-42B0-83D9-A101299C0B12">pfnCheckMultiPlaneOverlaySupport (DXGI)</a> function to check details on hardware support for multiplane overlays.


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function to create the display device. 


### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the hardware support is queried.


### -field NumPlaneInfo

[out] The number of overlay planes that the hardware supports.


### -field pPlaneInfo

[out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780281">DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO</a> structure that specifies support attributes that the hardware provides for multiplane overlays.


### -field Supported

[out] <b>TRUE</b> if the hardware supports multiplane overlays, otherwise <b>FALSE</b>.



## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780281">DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO</a>



<a href="https://msdn.microsoft.com/9062BB6D-7B52-42B0-83D9-A101299C0B12">pfnCheckMultiPlaneOverlaySupport (DXGI)</a>
 

 

