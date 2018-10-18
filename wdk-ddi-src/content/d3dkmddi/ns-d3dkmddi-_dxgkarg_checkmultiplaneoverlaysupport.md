---
UID: NS:d3dkmddi._DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
title: "_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT"
author: windows-driver-content
description: Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport function to check details on hardware support for multiplane overlays.
old-location: display\dxgkarg_checkmultiplaneoverlaysupport.htm
ms.assetid: BAFC7DD1-56F8-47CE-8914-54531BBC3165
ms.date: 5/10/2018
ms.keywords: "*IN_OUT_PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure [Display Devices], PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure pointer [Display Devices], _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, d3dkmddi/PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, display.dxgkarg_checkmultiplaneoverlaysupport"
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	D3dkmddi.h
api_name:
-	DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
---

# _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure


## -description


Used in a call to the <a href="https://msdn.microsoft.com/8332DD64-B75E-40A4-9D98-3406187150F2">DxgkDdiCheckMultiPlaneOverlaySupport</a> function to check details on hardware support for multiplane overlays.


## -struct-fields




### -field PlaneCount

The number of overlay planes that the hardware supports.


### -field pPlanes

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn305132">DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE</a> structure that specifies support attributes that the hardware provides for multiplane overlays.


### -field Supported

<b>TRUE</b> if the hardware supports multiplane overlays, otherwise <b>FALSE</b>.


### -field ReturnInfo

Specifies limitations on hardware support of multiplane overlays.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn305132">DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE</a>



<a href="https://msdn.microsoft.com/8332DD64-B75E-40A4-9D98-3406187150F2">DxgkDdiCheckMultiPlaneOverlaySupport</a>
 

 

