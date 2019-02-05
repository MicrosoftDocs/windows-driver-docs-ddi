---
UID: NS:d3dumddi._D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT
title: _D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT (d3dumddi.h)
description: Used in a call to the pfnCheckMultiPlaneOverlaySupport (D3D) function to check details on hardware support for multiplane overlays.
old-location: display\d3dddiarg_checkmultiplaneoverlaysupport.htm
tech.root: display
ms.assetid: e5b6c24a-a3a5-4736-b9ee-ebb992070a83
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT, D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT structure [Display Devices], _D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT, d3dumddi/D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT, display.d3dddiarg_checkmultiplaneoverlaysupport
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT
---

# _D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT structure


## -description


Used in a call to the <a href="https://msdn.microsoft.com/A439E695-D374-439A-8A69-6D4E247FF134">pfnCheckMultiPlaneOverlaySupport (D3D)</a> function to check details on hardware support for multiplane overlays.


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
 

 

