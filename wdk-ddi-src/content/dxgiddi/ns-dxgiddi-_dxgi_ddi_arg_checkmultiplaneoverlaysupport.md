---
UID: NS:dxgiddi._DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT
title: "_DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT"
author: windows-driver-content
description: Used in a call to the pfnCheckMultiPlaneOverlaySupport (DXGI) function to check details on hardware support for multiplane overlays.
old-location: display\dxgi_ddi_arg_checkmultiplaneoverlaysupport.htm
old-project: display
ms.assetid: 1b339a88-9c05-4b57-9044-b00ef1c305fb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgi_ddi_arg_checkmultiplaneoverlaysupport, DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT, _DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT, dxgiddi/DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dxgiddi.h
apiname:
-	DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT
---

# _DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT structure


## -description


Used in a call to the <a href="https://msdn.microsoft.com/9062BB6D-7B52-42B0-83D9-A101299C0B12">pfnCheckMultiPlaneOverlaySupport (DXGI)</a> function to check details on hardware support for multiplane overlays.


## -syntax


````
typedef struct _DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT {
  DXGI_DDI_HDEVICE                                     hDevice;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID                       VidPnSourceId;
  UINT                                                 NumPlaneInfo;
  DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO *pPlaneInfo;
  BOOL                                                 Supported;
} DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the hardware support is queried.


### -field NumPlaneInfo

[out] The number of overlay planes that the hardware supports.


### -field pPlaneInfo

[out] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_check_multiplaneoverlaysupport_plane_info.md">DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO</a> structure that specifies support attributes that the hardware provides for multiplane overlays.


### -field Supported

[out] <b>TRUE</b> if the hardware supports multiplane overlays, otherwise <b>FALSE</b>.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_check_multiplaneoverlaysupport_plane_info.md">DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/9062BB6D-7B52-42B0-83D9-A101299C0B12">pfnCheckMultiPlaneOverlaySupport (DXGI)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

