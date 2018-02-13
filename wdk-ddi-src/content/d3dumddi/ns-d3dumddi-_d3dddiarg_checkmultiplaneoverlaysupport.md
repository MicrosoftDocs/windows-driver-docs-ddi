---
UID: NS:d3dumddi._D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT
title: "_D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT"
author: windows-driver-content
description: Used in a call to the pfnCheckMultiPlaneOverlaySupport (D3D) function to check details on hardware support for multiplane overlays.
old-location: display\d3dddiarg_checkmultiplaneoverlaysupport.htm
old-project: display
ms.assetid: e5b6c24a-a3a5-4736-b9ee-ebb992070a83
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddiarg_checkmultiplaneoverlaysupport, D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT structure [Display Devices], d3dumddi/D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT, _D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT, D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dumddi.h
apiname:
-	D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT
---

# _D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT structure


## -description


Used in a call to the <a href="https://msdn.microsoft.com/A439E695-D374-439A-8A69-6D4E247FF134">pfnCheckMultiPlaneOverlaySupport (D3D)</a> function to check details on hardware support for multiplane overlays.


## -syntax


````
typedef struct _D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID                     VidPnSourceId;
  UINT                                               NumPlanes;
  D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO *pPlanes;
  BOOL                                               Supported;
} D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT;
````


## -struct-fields




### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the hardware support is queried.


### -field NumPlanes

[out] The number of overlay planes that the hardware supports.


### -field pPlanes

[out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780232">D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO</a> structure that specifies support attributes that the hardware provides for multiplane overlays.


### -field Supported

[out] <b>TRUE</b> if the hardware supports multiplane overlays, otherwise <b>FALSE</b>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh780232">D3DDDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO</a>



<a href="https://msdn.microsoft.com/A439E695-D374-439A-8A69-6D4E247FF134">pfnCheckMultiPlaneOverlaySupport (D3D)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

